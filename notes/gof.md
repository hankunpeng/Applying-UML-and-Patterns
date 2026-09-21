# GoF 模式速查 · GoF Pattern Quick Reference

> **定位**：GoF 是 GRASP 的**特化**。Larman 自己举过例子：Adapter = Indirection + Protected Variations；一句「用 Abstract Factory 生成的 Strategy 来支持对 X 的 Protected Variations」，能把一整块设计意图压缩传递出去。
>
> Where this sits: GoF patterns are specializations of GRASP. Larman puts it directly — Adapter *is* Indirection plus Protected Variations. A single sentence like "use a Strategy produced by an Abstract Factory to support Protected Variations on X" carries a whole block of design intent.

所以这份笔记不重复 23 个模式的实现细节（到处都有），只记三件事：**什么时候该想到它、它违反了会怎样、它对应哪个 GRASP**。

So this note does not restate implementations of the 23 patterns — those are everywhere. It records three things only: when to think of it, what breaks without it, and which GRASP principle it maps to.

## 创建型 / Creational

| 模式 | 解决什么 | 何时该想到 | 对应 GRASP |
| --- | --- | --- | --- |
| Factory Method | 把实例化推迟到子类 | 构造逻辑有两种以上实现 | Creator + PV |
| Abstract Factory | 创建一族相关对象 | 需要整族替换（换数据库、换主题、换云厂商） | Creator + PV |
| Builder | 分步构造复杂对象 | 参数多、可选组合多、构造过程要分阶段 | Pure Fabrication |
| Prototype | 通过复制创建对象 | 构造成本高，且差异很小 | Creator |
| Singleton | 保证唯一实例 | **几乎不该用** —— 交给依赖注入容器 | （反模式警示） |

## 结构型 / Structural

| 模式 | 解决什么 | 何时该想到 | 对应 GRASP |
| --- | --- | --- | --- |
| Adapter | 让不兼容接口能协作 | 接第三方 SDK、遗留系统 | Indirection + PV |
| Facade | 为子系统提供统一入口 | 外部依赖面太宽，想收窄 | Low Coupling |
| Proxy | 控制对对象的访问 | 延迟加载、访问控制、远程调用 | Indirection + PF |
| Decorator | 动态叠加职责 | 用继承会导致类爆炸 | PV（替代继承） |
| Composite | 树形「整体—部分」 | 目录、菜单、组织架构、表达式树 | Polymorphism |
| Bridge | 抽象与实现各自独立演化 | 两个维度同时在变 | PV |
| Flyweight | 共享大量细粒度对象 | 海量对象且状态可外置 | Pure Fabrication |

## 行为型 / Behavioral

| 模式 | 解决什么 | 何时该想到 | 对应 GRASP |
| --- | --- | --- | --- |
| Strategy | 算法可替换 | 同一件事有多种算法/规则/费率 | Polymorphism + PV |
| Observer | 状态变化通知多方 | 一处变更触发多处联动 | Indirection + PV |
| Template Method | 骨架固定、步骤可变 | 多个流程主体相同只差几步 | PV |
| Command | 把请求变成对象 | 需要排队、撤销、重做、事务、日志 | Pure Fabrication |
| State | 状态决定行为 | 出现状态机的 switch，且状态会增长 | Polymorphism |
| Chain of Responsibility | 请求沿链传递 | 多个处理器，谁处理由运行时决定 | Indirection |
| Mediator | 用中介收敛对象间交互 | 对象之间互相引用成网 | Indirection + Low Coupling |
| Memento | 保存与恢复状态 | 需要撤销、快照 | Pure Fabrication |
| Iterator | 统一遍历方式 | 需要屏蔽集合内部结构 | Indirection |
| Visitor | 给结构加新操作而不改结构 | 结构稳定、操作频繁增加 | （慎用，违背直觉） |
| Interpreter | 解释一门小语言 | 规则引擎、DSL | Polymorphism + Composite |

---

## 日常真正高频的六个 / The six you actually use

按使用频率排序，其余的在用到时查表即可。

1. **Strategy** — 同一件事有多种做法（费率、排序、路由、审核规则）。触发信号：一段 `switch` 的分支在按「策略」而非「数据」增长。反模式：只有一种实现就先上 Strategy。
2. **Adapter** — 任何第三方依赖的边界都该有一层。触发信号：业务代码里出现了第三方类型。反模式：Adapter 里塞业务逻辑，变成第二个实现。
3. **Facade** — 子系统对外只留一个入口。触发信号：调用方为了做一件事要认识五六个类。反模式：Facade 变成上帝类。
4. **Observer / 事件** — 一处变更引发多处联动。触发信号：`afterCreate` 里直接调五个下游。反模式：同步链式调用没做失败隔离，一个下游挂掉全链路失败。
5. **Command** — 需要撤销、重做、排队、审计。触发信号：操作需要被记录或回滚。
6. **Template Method** — 流程骨架固定。触发信号：几个流程长得很像，只差中间几步。反模式：抽象类的钩子越加越多，最后子类只重写一个方法却被迫理解全部钩子。

## 与 agent 协作时的注意 / Working with agents

- **agent 很爱套模式。** 检查方法只有一个：让它说出这个模式挡住了什么变化。答不出就删掉 —— 那是装饰，不是设计。
- **Singleton 是 agent 的常见默认值**（配置、连接池、缓存）。一律改成构造注入，全局可变状态是单测的头号杀手。
- **警惕三层抽象工厂。** agent 有时会为一个实现造出接口 + 抽象工厂 + 工厂方法。硬规则：先给出两个真实实现，再谈抽象。
- **让 agent 报告模式选择。** 要求它在方案里写「这里用了 X 模式，因为变化点是 Y」，这句话能暴露绝大多数过度设计。
