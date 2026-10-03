---
name: ata
description: "Cross-agent master/worker protocol. The master works with the user, writes task cards and reviews results; workers, often other tools or cheaper models, each execute one task card and report in it. Use when the user enables ata, says you are the ata master or worker (e.g. 「你是 ata 的 worker。读取 docs/tasks/T-###.md 并执行。」), asks you to execute a task card under docs/tasks/, or wants one agent to plan and another to implement."
---

# aTa

aTa 是跨 agent 的协作协议。参与项目的 agent 分为两个角色，通常运行在不同的工具或模型上：

- `master`：直接和用户对话，负责对齐方向、写计划和任务卡、验收结果、维护项目文档。
- `worker`：接收 master 写的任务卡，在卡片划定的范围内施工、验证，并在卡片末尾汇报。

两个角色不直接对话，靠项目里的文档交接：master 把任务写成任务卡，由用户转交给 worker；worker 把汇报写在卡片末尾。

## 1. 确认身份

- 用户指明了你是 `master` 或 `worker`，按指明的身份工作。
- 用户让你执行一张任务卡（`docs/tasks/T-###.md`），你就是 `worker`。转手的话通常是：「你是 ata 的 worker。读取 `docs/tasks/T-###.md` 并执行。」
- 都没有，问用户：「这次我是 ata 的 master 还是 worker？」不要根据项目里有哪些文档自己判断。

## 2. 读取角色卡

确认身份后，读取对应的角色卡。路径相对于 ata skill 的根目录，也就是本文件所在的目录。

- `master` 读取 `references/master.md`。
- `worker` 读取 `references/worker.md`。

角色卡要完整读完。只读自己的角色卡：另一个角色的规则不适用于你，读了只会占用上下文。之后还要读哪些文件，由角色卡指明。
