# Claude Skill 使用说明

本目录用于存放 Claude 适配版技能文件。计划中的技能文件路径：

```text
skill_for_claude/SKILL.md
```

## 文件格式

Claude Skill 以一个包含 `SKILL.md` 的目录为基本单元。`SKILL.md` 使用 YAML frontmatter 描述技能名称和用途，后接 Markdown 指令正文，例如：

```yaml
---
name: readable-code
description: Apply clear, readable, pragmatic design principles when generating, modifying, or reviewing code.
---
```

当前技能只需要 `SKILL.md`；如以后需要辅助脚本、参考资料或资源文件，可再添加 `scripts/`、`references/` 或 `assets/`。

## 使用方法

1. 将 Claude 适配版 `SKILL.md` 放在本目录。
2. 按你使用的 Claude 产品所支持的 Skills 导入方式，上传或安装包含该文件的技能目录；不同产品的入口和个人/团队管理方式可能不同。
3. 在 Claude 中发起代码生成、修改、重构或审查任务，并让它使用 `readable-code` 技能；如果产品支持按描述自动匹配，也可由 Claude 根据技能描述选择。

> 本仓库目录是技能源文件的存放位置，不一定是 Claude 客户端的直接安装路径。使用前请以对应 Claude 产品当前的 Skills 文档或界面为准。
