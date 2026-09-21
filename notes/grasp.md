# GRASP 九模式 · The Nine GRASP Patterns

> **为什么这份笔记值得写**：低耦合高内聚你在一百本书里都能读到，但「职责该怎么分配」这套可命名的启发式，市面上只有 Larman 系统讲过。GoF 是**结构模板**（遇到某类场景套某个形状），GRASP 是**分配原则**（这个功能该放进哪个对象）——后者是你每天、每秒都在做的微观决策。
>
> Why this note exists: everyone teaches low coupling and high cohesion, but only Larman systematically teaches how to *assign responsibilities*. GoF patterns are structural templates; GRASP are assignment principles. You apply the latter constantly.

Larman 自己说过：模式的名字不重要，重要的是它们**逼你对每一步设计决策给出理由**（书中称 No-Magic Zone）。名字只是让理由可以被讨论。

Larman himself says the pattern names don't matter — what matters is that they force you to give a reason for every design decision (he calls this the "no-magic zone"). Names just make reasons discussable.

## 速查 / Quick reference

| 模式 | 解决什么 | 一句话 |
| --- | --- | --- |
| Information Expert 信息专家 | 这个方法该放哪 | 谁拥有完成它所需的信息，就放谁那 |
| Creator 创建者 | 谁负责 new | 谁包含、记录、紧用、拥有初始化数据，谁来创建 |
| Controller 控制器 | 系统事件谁先接 | 用代表用例的门面对象，且只做转发 |
| Low Coupling 低耦合 | 依赖怎么收 | 依赖要少、要稳、要单向 |
| High Cohesion 高内聚 | 类该多大 | 职责要在功能上高度相关 |
| Polymorphism 多态 | 类型分支怎么办 | 用行为的变化替代类型的判断 |
| Pure Fabrication 纯虚构 | 职责无处安放时 | 造一个领域里不存在的类来扛 |
| Indirection 间接 | 双方怎么解耦 | 引入中间对象承担连接 |
| Protected Variations 受保护变化 | 变化怎么隔离 | 用稳定接口包住不稳定之处 |

---

## 1. Information Expert 信息专家

- **一句话**：把职责分配给拥有完成它所需信息的那个对象。
- **决策问题**：「要完成这件事，需要哪些数据？这些数据现在归谁管？」
- **判断规则**：先找出所需信息的来源，方法就落在那儿。
- **反例**
  ```ts
  // 打折逻辑散在调用方，因为「订单知道自己的条目与总额」
  class CheckoutHandler {
    total(order: Order) {
      let sum = 0
      for (const line of order.lines) sum += line.price * line.qty
      return sum * discountRateFor(order.customerLevel)
    }
  }
  ```
- **修正**：`order.total()` —— 订单自己拥有条目与客户等级。
- **和 agent 协作 / With agents**：让 agent 先回答「这件事需要的信息现在在谁手里」，再决定方法放哪。反向用法很有效：看到 agent 把逻辑塞进 `utils/` 或 `helper.ts`，就问它一句「这些数据现在归谁管」。

## 2. Creator 创建者

- **一句话**：满足以下之一，就由 B 来创建 A —— B 包含/聚合 A、B 记录 A、B 紧密使用 A、B 拥有 A 的初始化数据。
- **决策问题**：「谁天然拥有这个新对象所需的信息？」
- **判断规则**：优先让自然容器去 new；上述四条都不满足时才引入工厂。
- **反例**：为每一个类都配一个 `XxxFactory`，哪怕调用方本来就是唯一持有构造数据的对象。
- **修正**：先按 Creator 规则直接 new，只有构造逻辑本身变复杂（多实现、需要配置、生命周期管理）时才升级为 Factory。
- **和 agent 协作**：工厂满天飞是典型信号。明确要求「先按 Creator 规则，只有规则都不满足时才引入 Factory」。

## 3. Controller 控制器

- **一句话**：用一个代表系统/用例的门面对象接住外部事件，**它只做转发**。
- **决策问题**：「这个请求进来，第一个被叫到的是谁？」
- **判断规则**：控制器只做三件事 —— 解析入参、委派给领域对象、组装出参。
- **反例**：`OrderController` 里直接写校验、计算、查库、发消息，长几百行，成为「上帝控制器」。
- **修正**：控制器转发给 `OrderService`，业务规则下沉到 `Order` 等对象。
- **和 agent 协作**：agent 的默认产出常常是「一个 handler 包办一切」。在 prompt 里写死：controller 只做解析、委派、组装，不允许出现业务规则。

## 4. Low Coupling 低耦合

- **一句话**：让依赖尽量少、尽量稳定、尽量单向。
- **决策问题**：「如果我改这个模块，会连带多少个模块？」
- **判断规则**：不是追求零耦合，而是减少**与不稳定之物的耦合**；依赖方向应指向更稳定的一侧。
- **反例**：业务层直接 import 数据库客户端与 HTTP 客户端；模块之间互相 import 成环。
- **修正**：依赖倒置 —— 业务层定义接口，基础设施在外层实现。
- **和 agent 协作**：让 agent 输出一份依赖关系列表与方向，然后检查三件事：有无环、业务层是否 import 了基础设施、依赖是否指向稳定的一侧。

## 5. High Cohesion 高内聚

- **一句话**：一个类的职责应在功能上高度相关，方法数量适中。
- **决策问题**：「这个类能用一句话说清自己负责什么吗？」
- **判断规则**：说不出来的就是内聚有问题。两个极端都不行 —— 上帝类（几百行、方法互不相关）与贫血类（只有 getter/setter）。
- **反例**：`UserManager` 同时管认证、资料、积分、通知。
- **修正**：按**变化原因**拆，不按代码长短拆。
- **和 agent 协作**：要求 agent 为每个类给一句职责描述。给不出来、或描述里出现「和 / 以及」，就是内聚有问题。

## 6. Polymorphism 多态

- **一句话**：当行为随类型变化时，用多态替代基于类型的条件分支。
- **决策问题**：「如果新增一种类型，我是加代码还是改代码？」
- **判断规则**：分支在按类型增长且预期会继续增长 → 用多态。只有两三个分支且不会增长 → switch 更简单，别急着改。
- **反例**
  ```ts
  function ship(kind: string) {
    if (kind === 'air') { /* ... */ } else if (kind === 'sea') { /* ... */ }
  }
  ```
- **修正**：`ShippingMethod` 接口 + `AirShipping` / `SeaShipping`。
- **和 agent 协作**：「看到按类型分派的 switch，就提出多态方案，并说明理由」—— 但同时让它说明分支是否真的会增长，避免过度设计。

## 7. Pure Fabrication 纯虚构

- **一句话**：当按 Information Expert 分配会破坏内聚或耦合时，造一个领域模型里并不存在的类来承担职责。
- **决策问题**：「这个职责确实不属于任何领域概念吗？」
- **判断规则**：这是**必要之恶**，目的是让领域对象保持纯净。典型产物：`Repository`、`Mapper`、`Logger`、策略对象。
- **反例**：把本该属于 `Order` 的计价逻辑抽到 `OrderHelper`，`Order` 退化成只有字段的数据袋 —— 这是**贫血领域模型**，是滥用而非应用。
- **修正**：先按 Expert 找归属；确认无处可放（职责是技术性的、或跨多个领域对象的），才 Pure Fabrication。
- **和 agent 协作**：这是 agent 最容易滥用的模式。它天然倾向把逻辑抽进 `Service` / `Util` / `Helper`。加一条硬约束：新增任何非领域类，都要说明「为什么这个职责不属于任何领域概念」。

## 8. Indirection 间接

- **一句话**：在两者之间插入中间对象，让双方不直接依赖。
- **决策问题**：「这层间接挡住了什么变化？」
- **判断规则**：典型手段 —— Adapter、Broker、事件总线、消息队列。代价是理解成本上升，所以只在该解耦的时候加。
- **反例**：为了「以后可能换成别的库」，给每个第三方依赖都套一层 wrapper，结果这层永远只有一个实现。
- **修正**：先确认变化点真实存在，再引入间接层（见 Protected Variations）。
- **和 agent 协作**：agent 很喜欢「加一层 wrapper 解决一切」。检查方法：让它说出这层隔离了什么变化，答不出就删掉。

## 9. Protected Variations 受保护变化

- **一句话**：识别变化点与演化点，用稳定接口把它们包住，让变化不外溢。
- **决策问题**：「哪些东西最可能变？变的时候会波及多少代码？」
- **判断规则**：这是**最上位的一个** —— 多态、纯虚构、间接、依赖倒置、面向接口编程，本质上都是它的特化手段。常见变化源：外部系统与第三方 API、算法与规则、数据格式、法律法规。
- **反例**：支付逻辑硬编码在订单服务里，接第二个支付渠道要改订单服务。
- **修正**：抽象出 `PaymentGateway` 接口，把易变的渠道实现推到边界外。
- **和 agent 协作**：最有价值的一句 prompt —— 「动手前先列出这个功能里最可能变化的三个点，说明你会用什么稳定接口包住它们」。这句话能把 agent 从「写完能跑」拉到「写得能改」。

---

## 决策顺序 · Order of decisions

拿到一个功能，按这个顺序问，不要跳步：

1. **Information Expert** — 需要的信息在谁手里？职责先落在那儿。
2. **Creator** — 谁来创建新对象？
3. **Controller** — 外部事件由谁接住？确认它只做转发。
4. **Low Coupling / High Cohesion** — 回头检查：依赖方向和类内聚是否被破坏。
5. **Protected Variations** — 变化点在哪？用 Polymorphism / Pure Fabrication / Indirection 去包住它。

前四步定**结构**，第五步定**韧性**。多数 agent 产出的代码缺的是第 5 步 —— 它能跑，但第一个需求变更就会把它压塌。

The first four steps decide **structure**; the fifth decides **resilience**. Most agent output is missing step 5 — it runs, but the first requirement change collapses it.
