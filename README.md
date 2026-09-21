# UML 和模式应用 · 读书笔记

Reading notes for Craig Larman, *Applying UML and Patterns: An Introduction to Object-Oriented Analysis and Design and Iterative Development*, 3rd Edition (2004, 736 pages).

原著 PDF 见 `book/`。

## 立场 / Position

AI 写代码的能力把「执行性知识」（UML 语法、API、框架用法、画图）压到了接近零成本，而「判断性知识」（职责怎么分、变化怎么隔离、边界划在哪）成了唯一瓶颈。

Coding agents have driven the cost of executable knowledge — UML syntax, APIs, framework usage, diagramming — to near zero. Judgment — how responsibilities are assigned, how variation is isolated, where boundaries go — is now the only bottleneck.

这本书 736 页里，真正属于后者的不到一半。所以这个仓库不摘抄全书，只做一件事：**把书里值得内化的部分，改造成能直接用的判断工具。**

Less than half of the book's 736 pages belong to the second category. So this repo does not summarize the book. It converts the parts worth internalizing into judgment tools you can actually use.

## 内容分层 / Triage

| 处理 | 内容 | 书内页码 |
| --- | --- | --- |
| 跳过 Skip | UML 表示法：类图、顺序图、包图、交互图、活动图、状态机图、部署与构件图 | 11, 89, 177, 201, 221, 249, 477, 485, 621 |
| 速读 Skim | UP 过程、迭代与项目管理、operation contracts 等文档制品 | 17, 31, 33, 181, 326, 501, 673 |
| 精读 Study | 领域模型、需求到设计、GRASP、GoF 应用、架构分析、持久层框架 | Ch9, 12, 17, 18, 25, 26, 33, 34, 38 |

跳过不等于无用，而是「不再需要由人记住」：图的语法交给 AI，你只需要知道有哪几种图、各自表达什么。

Skip does not mean useless. It means no longer worth holding in your head: let the agent handle diagram syntax, and keep only the knowledge of which diagram types exist and what each expresses.

## 精读路线 / Study route

1. **Ch17 + Ch18** — GRASP 前五个模式与设计实例
2. **Ch25** — GRASP 后四个模式
3. **Ch26** — GoF 模式作为 GRASP 的特化
4. **Ch9 + Ch12** — 领域模型，以及从需求到设计的迭代
5. **Ch33 + Ch34** — 架构分析与逻辑架构
6. **Ch38** — 综合案例：用模式组合设计持久层

## 目录 / Contents

- `notes/principles.md` — 设计原则：触发场景与反例
- `notes/grasp.md` — GRASP 九模式
- `notes/gof.md` — GoF 模式速查
- `notes/review-checklist.md` — 审查 AI 产出的清单
- `notes/design-prompts.md` — 给编码 agent 的设计指令模板

## 进度 / Progress

- [x] 目录重组与分层路线
- [x] 原则笔记：触发场景 + 反例
- [x] GRASP 九模式
- [x] GoF 速查
- [x] AI 代码审查清单
- [ ] 设计指令模板
