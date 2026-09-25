---
name: ata
description: "Coordinate agent and other agent as master/worker agents for project planning, task dispatch, implementation handoff, review, and document maintenance. Use when the user enables ata, asks you to act as master or worker, wants agent and other agent to collaborate, or needs project plans and worker tasks prepared for cross-agent development."
---

# aTa

aTa 是不同agent间的协作协议。它把参与项目的 agent 分为两个角色：

- `master`：直接和用户对话，负责项目方向、计划编写、任务拆分、任务下发、结果审查和文档治理。
- `worker`：接收 master 的任务单，负责在明确边界内实现、审查、研究、验证和汇报。

## 启动

### 1.先确认当前身份：

- 如果用户已经明确指明你是 `master` 或 `worker`，直接按该身份工作。
- 如果身份不清楚，向用户询问你当前的身份定位。

### 2.确认身份后读取对应身份文件，确认自己具体的职责和工作流：

- `master` 读取 `references/master.md`。
- `worker` 读取 `references/worker.md`。
