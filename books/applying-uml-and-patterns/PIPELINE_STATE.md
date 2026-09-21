# PIPELINE_STATE — applying-uml-and-patterns

- **book**: Applying UML and Patterns, 3rd Ed. (Craig Larman, 2004)
- **source**: `/Users/alex/github/hankunpeng/Applying-UML-and-Patterns/Applying UML and Patterns 3rd Edition.pdf`
- **scope**: Ch9 / Ch12 / Ch17 / Ch18 / Ch25 / Ch26 / Ch33 / Ch34 / Ch38（PDF 218–868，309 页，417,332 字符）
- **output mode**: single（用户已确认）
- **updated**: 2026-09-21

## 进度

| 阶段 | 状态 | 产物 |
|---|---|---|
| 准备：文本抽取 | ✅ done | `source/ch*.txt`（9 章）+ `source.md` |
| 准备：分块 + 索引 | ✅ done | `.cangjie/chunks/chunks.jsonl`（474 elements → 104 chunks）+ `.cangjie/lexical.sqlite` |
| 阶段 0 整书理解 | ✅ done（`BOOK_OVERVIEW.md` 已生成，待用户确认） | `BOOK_OVERVIEW.md` |
| 阶段 1 并行提取 | ⬜ pending | `candidates/*.md` |
| 阶段 1.5 三重验证 | ⬜ pending | `verified.md` + `rejected/` |
| 阶段 1.6 晋级门 | ⬜ pending | `.cangjie/capabilities/destinations.json` |
| 阶段 2 RIA++ 能力卡 | ⬜ pending | `.cangjie/capabilities/cards/*.md` |
| 阶段 3 Zettelkasten | ⬜ pending | `GLOSSARY.md` + `also_read` |
| 阶段 4 压力测试 | ⬜ pending | 评测用例 |
| 阶段 5 编译交付 | ⬜ pending | `DIGEST.md` + 编译产物 |

## 环境备忘

- Python: `/Users/alex/.workbuddy/binaries/python/envs/default/bin/python`（已装 pypdf / pyyaml / jsonschema）
- cangjie skill 目录: `~/.workbuddy/skills/cangjie-skill/`
- 章节页范围记录在 `source/_chapters.json`
