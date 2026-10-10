# 项目文档总览

本文给 master 看：项目里有哪些文档，每类信息放在哪里。写或改某份文档前，读下表里它的写法文件。

## 原则

- 一类信息只放一处，其他文档只写路径，不复述内容。拿不准放哪里时，按下面两张表判断。
- 文档放在 `docs/` 下；只有 `AGENTS.md`、`CLAUDE.md`、`README.md` 放在项目根目录。
- 只写整理过的结论，不贴对话、汇报原文和终端输出。只为一条主线临时写的说明，主线收口时删掉。

## 标准文档

使用 ata 的项目都有这些文档，初始化时一次建好（`workflows/init.md`）。已经在用 ata 的项目缺了哪一份，按它的写法文件补建。

| 文档 | 放什么 | 谁写 | 写法 |
|---|---|---|---|
| `AGENTS.md` | 项目定位、文档入口、工程原则 | master | `references/docs/agents-md.md` |
| `docs/PROJECT_PLAN.md` | 目标、路线图、范围、架构、项目级验收 | master | `references/docs/project-plan.md` |
| `docs/STATUS.md` | 当前状态 | master | `references/docs/status.md` |
| `docs/decisions.md` | 用户确认的决定和理由 | master | `references/docs/decisions.md` |
| `docs/scratchpad.md` | 讨论中已确认、还没整理进正式文档的内容 | master；用户也可以直接改 | `references/docs/scratchpad.md` |
| `docs/tasks/T-###/T-###.md` | 任务定义、当前状态和最终收口摘要；目录在派卡时建 | master | `references/docs/task-card.md` |
| `docs/tasks/T-###/worker-NN.md` | 本轮工作汇报 | worker | `references/worker.md` |
| `docs/tasks/T-###/review-NN.md`、`docs/tasks/T-###/rework-NN-request.md` | 本轮审查报告、返工要求；按需建立 | master | `references/docs/task-card.md` |
| `docs/ata/` | 两个角色的实践手册、候选经验的收件箱 | master | `references/docs/practices.md` |

## 按需文档

| 文档 | 什么时候建 | 谁写 | 写法 |
|---|---|---|---|
| 主线计划：`docs/phaseN_plan.md`、`docs/<主题>_plan.md` | 一条主线开始规划时 | master | `references/docs/plan.md` |
| `docs/module_map.md` | 项目有了源码 | worker，由任务卡安排 | `references/docs/module-map.md` |
| `README.md` | 有了可以交给别人使用的功能 | worker，由任务卡安排 | `references/docs/readme-md.md` |
| 领域规格：`docs/<领域>.md` | 某个领域的行为细到计划里写不下 | master；从现有代码整理时派卡 | `references/docs/spec.md` |

项目原有的其他文档（例如代码规范 `docs/code_spec.md`）按原来的写法维护，在 `AGENTS.md` 的文档入口里登记。
