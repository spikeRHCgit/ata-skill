# aTa Skill

`aTa` 是一份跨 Agent 协作协议。它将参与项目的 Agent 划分为两种角色：

- **master**：直接与用户沟通，负责方向对齐、计划、任务拆分、派发、验收和文档治理。
- **worker**：在明确边界内执行实现、研究、审查或验证，并向 master 汇报。

它的目标是让不同 Agent 框架之间也能使用一致、可交接的协作流程。

## 当前状态

实验阶段。协议会在实际项目中持续调试与调整；Git 提交记录变更历史，Git tag 标记稳定版本。

## 结构

```text
aTa/
├── SKILL.md                 # Skill 入口：确认身份，读取对应的角色卡
├── references/
│   ├── master.md            # master 角色卡
│   ├── worker.md            # worker 角色卡
│   ├── docs.md              # 项目文档总览：有哪些文档、各放什么
│   └── docs/                # 每份项目文档的写法
├── workflows/               # master 的工作流：初始化、规划、施工、计划外工作
├── assets/
│   └── codex-hooks.json     # Codex 上下文压缩后的提醒
├── README.md
└── LICENSE
```

## 安装

本 skill 通过 [`skills`](https://github.com/vercel-labs/skills) CLI 从 GitHub 安装：

```powershell
npx skills@latest add spikeRHCgit/ata-skill
```

安装器会让你选择目标 Agent、全局或项目范围，以及 symlink 或 copy 安装方式。查看可安装内容而不修改本机：

```powershell
npx skills@latest add spikeRHCgit/ata-skill --list
```

使用时由用户明确指定本轮身份：

- `master`：读取 [`references/master.md`](references/master.md)
- `worker`：读取 [`references/worker.md`](references/worker.md)

身份未明确时，Agent 应先询问：“本轮我是 master 还是 worker？”

## 维护与更新

维护者在本仓库修改、提交并推送：

```powershell
git add .
git commit -m "调整协作协议"
git push
```

已安装者通过以下命令拉取最新 skill：

```powershell
npx skills@latest update ata
```

若安装时选择了全局范围，则更新时加 `-g`：

```powershell
npx skills@latest update ata -g
```

## 许可证

本项目采用 [MIT License](LICENSE)。你可以自由使用、复制、修改、发布和再授权本项目，但必须保留原始版权与许可声明。
