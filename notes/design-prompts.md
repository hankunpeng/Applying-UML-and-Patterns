# 给编码 agent 的设计指令 · Design Prompts

> **Agent 产出的质量上限，等于你在 prompt 里给定的结构。** prompt 就是设计说明书，只是它不再用 UML 写。
>
> The ceiling on an agent's output quality equals the structure you hand it in the prompt. The prompt is the design spec — it just is not written in UML anymore.

这也是这本书在 AI 时代最实际的用途：过去你学 OOA/D 是为了自己画图和写代码，现在是为了**把结构写进 prompt**。

This is the most practical use of the book today: you used to learn OOA/D to draw and code yourself; now you learn it to write structure into a prompt.

## 三段式骨架 · Three-part skeleton

任何非平凡的需求，prompt 都该有这三段，顺序不能变：

1. **边界与依赖方向** — 哪些是领域对象，依赖指向哪一侧，禁止 import 什么
2. **变化点** — 最可能变的是什么，用什么稳定接口包住
3. **验收** — 测什么、以及让它先自查再动手

## 模板一：新功能开工 / New feature

```text
Implement <feature>.

Boundaries and dependency direction:
- Domain objects: <list>. They own the business rules.
- Domain layer must not import database, HTTP, or any SDK client.
  Define interfaces here; implement them in the outer layer.
- Entry point: <controller/service> only parses input, delegates,
  and assembles output.

Variation points:
- The three things most likely to change are <A>, <B>, <C>.
  Put a stable interface around each and tell me which one.

Acceptance:
- Tests assert behavior, not implementation details.
- Before writing code, report the class list with a one-sentence
  responsibility for each. Wait for my approval.
```

## 模板二：重构既有代码 / Refactor

```text
Refactor <module>. Do not change external behavior; tests must pass.

Report first, do not edit:
1. Each class and its one-sentence responsibility. Flag any needing "and".
2. Business logic that lives in utils, helpers, or managers — for each,
   say which domain object should own it instead (Information Expert).
3. Dependency direction violations: any business file importing
   infrastructure, and any cycles.
4. Every switch on a type — say whether the branches will keep growing
   and whether polymorphism is warranted.
5. Singletons and global mutable state, with the injection to replace each.

Then propose the smallest sequence of changes. Wait for my approval.
```

## 模板三：接入第三方依赖 / Integrating a third party

```text
Integrate <SDK/API>.

- No third-party types may appear outside the <adapter> boundary.
- Define the interface we depend on here; the adapter implements it.
- State what variation this boundary protects, and what happens to us
  when the vendor changes its API.
- Failure modes: list how each failure surfaces to callers, and which
  are retryable.
```

## 最有用的一句话 / The single most useful line

> Before writing code, list the three things most likely to change here and the stable interface that will contain each one.

这一句把 agent 从「写完能跑」拉到「写得能改」。Protected Variations 是整个 GRASP 里最上位的一条，而这句话是它在 prompt 里的可执行形式。

This single line pulls an agent from "runs when written" to "survives being changed". Protected Variations is the highest-level idea in GRASP, and this sentence is its executable form in a prompt.

## 坏 prompt 与好 prompt / Weak vs strong

**坏**：`Implement order checkout with payment support.`

会得到：一个 `CheckoutService` 包办校验、计价、调支付、写库、发通知；业务层直接 import HTTP 客户端；接第二个支付渠道要改核心文件。看起来完整，第一个变更就塌。

**好**：加上边界（领域对象清单 + 禁止 import）、变化点（支付渠道会变，用 `PaymentGateway` 包住）、验收（类清单 + 一句职责 + 等批准）。

差别不在字数，在于**你是否先想清楚了结构**。agent 不会替你做这个决定，它只会用最平庸的默认值填满空白。

The difference is not length. It is whether you settled the structure first. The agent will not make that decision for you; it fills the gap with the most mediocre default available.

## 元规则 / Meta rule

**让 agent 说出理由。** Larman 把这点叫 No-Magic Zone：设计里不允许有说不出理由的决策。落到 prompt 里就是一句要求 ——

Make the agent state reasons. Larman calls this the no-magic zone: no decision in a design is allowed to lack a reason. In a prompt it becomes one requirement:

```text
For every non-obvious choice in your solution, write one sentence
starting with "because". If you cannot, say so instead of inventing one.
```

说不出理由的地方，通常就是过度设计或照抄模板的地方。

Where it cannot produce a reason is usually where it over-designed or copied a template.
