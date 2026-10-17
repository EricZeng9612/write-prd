# write-prd

A Chinese-first Codex skill for writing and updating review-ready product requirements documents (PRDs).

用于编写、补全和修订全产品或单模块 PRD，支持 Web、SaaS、移动应用、小程序、桌面软件、后台服务／API，以及软硬件产品。

## 核心能力

- 用户任务 → 入口 → 主流程 → 六列功能点表 → 完成定义。
- 原型与功能逐项关联，区分目标需求、实际实现、设计差异和验收状态。
- 每次实际更新 PRD，都同步追加变更记录并保留历史。
- 无界面服务无需 UI 原型；纯软件无需硬件评审方。
- 资料不足时标注待确认，不编造负责人、指标或实现结果。

## 安装到 Codex

在 Codex 中输入：

```text
使用 $skill-installer 安装 GitHub 仓库 EricZeng9612/write-prd 中 skills/write-prd 目录下的技能。
```

已有同名技能时，先说明需要更新现有安装，避免重复安装。安装完成后在下一轮对话中使用。

技能目录包含：

```text
skills/write-prd/
├── SKILL.md
├── LICENSE
├── agents/openai.yaml
├── assets/prd-template.md
└── references/writing-patterns.md
```

## 使用

显式调用：

```text
使用 $write-prd，根据以下资料编写 Web 管理后台的用户管理模块 PRD，缺失信息标为待确认。
```

更新现有文档：

```text
使用 $write-prd，将这份 PRD 的保存失败逻辑改为保留输入并支持重试，同步更新流程、完成定义和变更记录。
```

自动选用已在 `agents/openai.yaml` 中通过 `policy.allow_implicit_invocation: true` 开启；当任务与技能描述匹配时，Codex 可自动选用。显式写出 `$write-prd` 可以明确指定该技能。

## 输出与集成

默认在聊天中交付，用户指定文件或远端文档时按要求输出。飞书读写是可选集成，需当前环境另有可用的 lark-doc 技能及对应访问权限；通用 PRD 编写无需飞书或 Figma。

本技能编写产品需求，不替代技术架构、接口协议或测试执行报告。写入远端文档与产品实际实现、部署和上线是不同状态。

## 公开内容边界

仓库仅包含通用技能、模板与写作示例，不包含内部 PRD 正文、私人文档链接、真实人员名单、凭据或截图。

## License

[MIT](LICENSE) © 2026 EricZeng9612
