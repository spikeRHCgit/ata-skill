# aTa Skill

`aTa` 是一份跨 Agent 协作协议。它将参与项目的 Agent 划分为两种角色：

- **master**：直接与用户沟通，负责方向对齐、计划、任务拆分、派发、验收和文档治理。
- **worker**：在明确边界内执行实现、研究、审查或验证，并向 master 汇报。

它的目标是让不同 Agent 框架之间也能使用一致、可交接的协作流程。

## 当前状态

实验阶段。协议会在实际项目中持续调试与调整；版本采用 npm 的 prerelease（例如 `0.1.0-beta.0`）标记。

## 结构

```text
aTa/
├── SKILL.md                 # Skill 入口与通用协作协议
├── references/
│   ├── master.md            # master 的职责与工作流
│   ├── worker.md            # worker 的职责与工作流
│   └── docs.md              # 项目文档的职责边界与审查规范
└── package.json             # npm / Pi package 元数据
```

## 使用

将整个 `aTa` 目录放入 Agent 框架扫描的 skills 目录，或将该目录链接到对应目录。使用时由用户明确指定本轮身份：

- `master`：读取 [`references/master.md`](references/master.md)
- `worker`：读取 [`references/worker.md`](references/worker.md)

身份未明确时，Agent 应先询问：“本轮我是 master 还是 worker？”

## 本地开发

以此仓库作为唯一源码目录。不同 Agent 的 skill 目录应通过 Windows junction 或符号链接指向该目录，避免维护多份副本。修改后重启对应 Agent，即可重新发现最新 skill 内容。

检查未来 npm 发布包会包含哪些文件：

```powershell
npm run check-package
```

## npm 发布

当前 `package.json` 中的 `private: true` 用于避免实验版本被误发布。准备公开发布前：

1. 将包名改为你自己的 npm scope，例如 `@your-npm-name/ata-skill`。
2. 删除 `private` 字段。
3. 登录并发布：

```powershell
npm login
npm version prerelease --preid=beta
npm publish --access public
```

详见 npm 官方文档与本仓库的提交历史。

## 许可证

尚未指定。公开使用、复制或贡献前，请先补充合适的开源许可证。
