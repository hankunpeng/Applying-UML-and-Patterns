# 设计原则 · Design Principles

> 用法：这份笔记不要求背诵。每条原则的价值有二 —— 一是给你**触发信号**，读到代码时能认出问题；二是给你**名字**，能一句话指出 agent 产出里的毛病。
>
> How to use this: nothing here needs memorizing. Each principle gives you (1) a trigger signal for recognizing problems when reading code, and (2) a name for calling out problems in agent output in one sentence.

## 取舍规则 · When principles collide

原则之间会打架。冲突时的默认优先级：

1. **低耦合 > DRY** — 错误的抽象比重复更难改。三处相似代码不一定该合并，先问：它们会不会因**同一个原因**而变化？
2. **YAGNI > OCP** — 出现第二个实现之前不加抽象层。扩展点由真实变化驱动，不由「以后可能」驱动。
3. **可测试 > 简洁** — 不可测的简洁是负债，不是资产。
4. **与现存代码一致 > 局部更优** — 除非你打算改掉全部调用点。

---

## SRP · 单一职责 / Single Responsibility

- **一句话**：一个类应该只有一个引起它变化的原因。
- **触发**：类名含 `Manager` / `Handler` / `Util` / `And`；改一个需求要动同一个类的多处；单测这个类需要 mock 三样互不相关的东西。
- **代价**：所有需求变更都撞进同一个文件，冲突和回归集中爆发。
- **反例**
  ```ts
  class OrderService {
    create() { /* ... */ }
    sendConfirmationEmail() { /* ... */ }  // 邮件模板变化也要改这里
    calculateTax() { /* ... */ }           // 税法变化也要改这里
  }
  ```
- **修正**：拆出 `OrderCreator` / `OrderNotifier` / `TaxCalculator`，由 `OrderService` 负责编排。

## OCP · 开放封闭 / Open–Closed

- **一句话**：对扩展开放，对修改封闭 —— 新需求加新代码，不改老代码。
- **触发**：一段 `if/else` 或 `switch` 的分支正在按某个**外部变化维度**增长（支付方式、渠道、租户）。
- **代价**：每新增一种就要改核心文件，核心区的稳定性被破坏。
- **反例**
  ```ts
  function pay(method: string) {
    if (method === 'alipay') { /* ... */ }
    else if (method === 'wechat') { /* ... */ }  // 每接一个渠道改一次
  }
  ```
- **修正**：定义 `PaymentMethod` 接口，每个渠道一个类，运行时注入。
- **注意**：别为还没发生的变化预留扩展点（见 YAGNI）。

## LSP · 里氏替换 / Liskov Substitution

- **一句话**：子类必须能替换父类，且不破坏调用方的预期。
- **触发**：子类把父类方法改成抛异常或空实现；调用方需要 `instanceof` 才能安全使用。
- **代价**：多态失效，调用方被迫了解具体实现，抽象层形同虚设。
- **反例**
  ```ts
  class ReadOnlyList extends List {
    add() { throw new Error('unsupported') }  // 调用方会崩
  }
  ```
- **修正**：`ReadOnlyList` 不该继承 `List`；抽出 `ReadableList` 作为共同父类型。

## ISP · 接口隔离 / Interface Segregation

- **一句话**：客户端不应依赖它用不到的方法。
- **触发**：实现一个接口时被迫写一堆空方法或 `throw not implemented`。
- **代价**：接口一改，所有实现者跟着改；实现里塞满无意义的桩。
- **反例**
  ```ts
  interface Worker { work(): void; eat(): void }
  class Robot implements Worker { eat() { /* 机器人不吃饭 */ } }
  ```
- **修正**：拆成 `Workable` / `Eatable`，`Robot` 只实现 `Workable`。

## DIP · 依赖倒置 / Dependency Inversion

- **一句话**：高层策略与底层细节都依赖抽象，抽象不依赖细节。
- **触发**：业务代码里直接 `new` 具体类、直接 import 数据库或 HTTP 客户端；想单测就得起真实服务。
- **代价**：业务逻辑无法脱离基础设施测试，也无法替换基础设施。
- **反例**
  ```ts
  class RegisterUser {
    private db = new PostgresClient()          // 依赖具体
    async run(u: User) { await this.db.insert(u) }
  }
  ```
- **修正**：构造注入 `UserRepository` 接口，具体实现放外层。

## 抽象原则 / Abstraction

- **一句话**：只暴露「做什么」，隐藏「怎么做」；抽象应按**变化原因**切分，而不是按代码长得像不像。
- **触发**：两段代码很相似，但业务含义不同 —— 这时别急着合并。
- **代价**：按表面相似做的抽象，会在两类需求同时到来时被撕开。
- **注意**：抽象是 GRASP 中 Protected Variations 在语言层的表达。

## DRY

- **一句话**：每条知识在系统里应该只有一处权威表达。
- **触发**：同一个业务规则（费率、阈值、校验）出现在多处。
- **代价**：改一处漏一处，产生行为漂移。
- **反例**：折扣计算在前端和后端各写一遍。
- **例外**：相似但变化原因不同的代码，重复优于合并（见取舍规则 1）。

## KISS

- **一句话**：能用直白写法解决，就不用巧妙写法。
- **触发**：为「通用性」引入的配置、泛型、反射，实际只有一个用例。
- **代价**：读代码的人必须先理解机制，才能理解业务。

## YAGNI

- **一句话**：没用到的能力不要先做。
- **触发**：「以后可能支持多语言 / 多租户 / 插件」，但当前只有一种。
- **代价**：推测式设计的代码路径没人走过，是未测试的负债。
- **注意**：区分**预留扩展点**（高成本：抽象层 + 配置）与**保持可替换**（低成本：依赖倒置）。后者可以做，前者不做。

## 得墨忒耳定律 / Law of Demeter

- **一句话**：只和直接的朋友说话，不写 `a.getB().getC().doSomething()`。
- **触发**：链式 getter 超过两级；为了调一个方法得先构造一串中间对象。
- **代价**：调用方被绑死在整条对象链的结构上，改结构就断一片。
- **反例**：`order.getCustomer().getWallet().charge(amount)`
- **修正**：`order.chargeToCustomerWallet(amount)` —— 把知识还给拥有它的对象（即 Information Expert）。

## Tell, Don't Ask

- **一句话**：告诉对象做什么，而不是先问它状态、再替它决定。
- **触发**：出现 `if (obj.getStatus() === X) { obj.doY() }` 这种外部决策。
- **代价**：对象的行为逻辑散落到调用方，内聚性被破坏。
- **反例**：`if (cart.items.length > 0) cart.checkout()`
- **修正**：`cart.checkout()`，由 cart 自己判断是否可结算。

## 关注点分离 / Separation of Concerns

- **一句话**：业务规则、流程编排、技术细节（持久化 / 传输 / 日志）分开放。
- **触发**：一个函数里既有校验、又有 SQL、又有响应组装。
- **代价**：换技术栈要动业务代码，改业务规则要动技术代码。

---

## 与 GRASP 的关系 · How this maps to GRASP

原则是**约束**，GRASP 是**动作**：原则描述「什么状态是好的」，GRASP 回答「面对一个具体功能，下一步该做什么」。

| 原则 | 对应的 GRASP 动作 |
| --- | --- |
| SRP / 对高内聚的诉求 | High Cohesion |
| DIP / ISP / OCP | Low Coupling + Protected Variations |
| Tell-Don't-Ask / LoD | Information Expert |
| 抽象原则 | Protected Variations |
