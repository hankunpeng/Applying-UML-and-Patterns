# AI 代码审查清单 · Reviewing Agent Output

> **为什么需要这份清单**：agent 的失败模式不是「写不出」，而是「写了一堆能跑、但改一处崩三处的代码」。人工逐行读它的产出不划算 —— 量大、且问题分布有规律。这份清单抓的就是那些规律。
>
> Why this exists: the failure mode of a coding agent is not failing to write code. It is writing code that runs but collapses on the first change. Reading its output line by line is a bad trade — the volume is high and the defects are patterned. This checklist targets those patterns.

**别拿它逐条核对自己的手写代码**，那太慢。它专为 agent 产出设计：量大、风格一致，清单才划算。

Do not use this to audit your own hand-written code line by line — too slow. It is built for agent output, where volume is high and style is uniform.

## 审查顺序 · Review in three passes

先看结构，再看变化点，最后看卫生。**顺序不能反** —— 结构错了，命名改得再漂亮也是白改。

Structure first, then variation points, then hygiene. Do not reverse the order: if the structure is wrong, no amount of renaming saves it.

---

## 第一遍：职责与边界 / Responsibilities and boundaries

- [ ] 每个类能用一句话说清自己的职责吗？（High Cohesion）
- [ ] 说不清、或描述里出现「和 / 以及」→ 内聚有问题
- [ ] 业务逻辑有没有被塞进 `utils/` `helper.ts` `XxxManager`？（Information Expert 被违反 → 贫血领域模型）
- [ ] 是否存在上帝类：单个类超过 300 行，或方法超过 15 个？
- [ ] controller / handler 里有没有业务规则？（Controller 只做解析、委派、组装）
- [ ] 依赖方向是否指向更稳定的一侧？业务层有没有直接 import 数据库或 HTTP 客户端？（Low Coupling）
- [ ] 是否存在循环依赖？
- [ ] 有没有 `a.getB().getC().doSomething()` 式链条？（Law of Demeter / Information Expert）

## 第二遍：变化点 / Variation points

- [ ] **动手前先问：这个功能里最可能变的三个点是什么？**（Protected Variations）
- [ ] 这些变化点有没有被稳定接口包住？
- [ ] 「新增一种 X」需要改动几个文件？大于 1 个就是 OCP 问题
- [ ] 有没有按类型分派的 `switch`，且分支预期会继续增长？（Polymorphism）
- [ ] 业务代码里是否出现了第三方 SDK 的类型？（Adapter / 边界泄漏）
- [ ] 有没有为单一实现造的接口、抽象工厂、wrapper 层？（YAGNI）
- [ ] 有没有 Singleton 或全局可变状态？一律改为构造注入
- [ ] 新增的非领域类，能否说明「为什么这个职责不属于任何领域概念」？（Pure Fabrication 是否滥用）

## 第三遍：卫生 / Hygiene

- [ ] 命名反映业务概念，而不是技术机制（`UserRepository` 好过 `UserDataAccessor`）
- [ ] 错误可区分、可恢复；有没有吞掉异常
- [ ] 有没有测试？测试断言的是行为还是实现细节？（后者会在重构时全部失效）
- [ ] 边界条件：空值、空集合、超长输入、并发
- [ ] 同一条业务规则是否出现在多处（DRY）—— 但先确认它们变化原因相同
- [ ] 注释解释「为什么」，而不是复述「做了什么」

---

## 严重度分级 / Severity

| 级别 | 问题 |
| --- | --- |
| **必修 Blocker** | 依赖方向反了（业务依赖基础设施）、循环依赖、业务规则散落在 util、全局可变状态 |
| **该改 Should fix** | 上帝类、controller 含业务规则、会增长的 switch、第三方类型泄漏、缺少边界层、无测试 |
| **可忍 Tolerable** | 命名、注释、三处以内且变化原因不同的重复 |

判断标准只有一条：**这个缺陷会在第一次需求变更时让我付出多大代价？**

One test for severity: how much will this defect cost me at the first requirement change?

## 让 agent 先自查 / Self-review prompt

在人工审查之前，先把下面这段贴给 agent。它能清掉七八成的表面问题，让清单只用来抓结构性缺陷。

Before reviewing manually, paste this to the agent. It clears most surface problems, so the checklist is spent on structural defects only.

```text
Before you present the solution, review it against this list and report
each item as OK or as a problem with the file and reason:

1. Every class has a single, one-sentence responsibility. Name any class
   whose description needs "and".
2. Business logic lives in domain objects, not in utils, helpers or
   managers. List any class that is only data plus getters/setters.
3. Controllers only parse input, delegate, and assemble output. No
   business rules.
4. Dependencies point toward the stable side. No business-layer file
   imports database or HTTP clients. No cycles.
5. Name the three things most likely to change here, and the stable
   interface that contains each one.
6. Adding a new variant of the main type requires adding code, not
   editing existing files. If not, say where.
7. No Singleton, no global mutable state; dependencies are injected.
8. Every non-domain class you introduced: state why the responsibility
   belongs to no domain concept.

Do not fix anything yet. Report first.
```

**关键在最后一句：先报告，别动手。** 让它一边改一边汇报，你会拿到一份自我辩护而不是一份问题清单。

The last line matters: report first, do not fix. If it fixes while reporting, you get a self-defense, not a defect list.
