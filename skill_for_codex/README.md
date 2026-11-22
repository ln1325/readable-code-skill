# Codex Skill 使用说明

本目录用于存放 Codex 适配版技能源文件。计划中的技能文件路径：

```text
skill_for_codex/SKILL.md
```

## 文件格式

Codex Skill 是一个目录，必须包含 `SKILL.md`。文件顶部使用 YAML frontmatter，至少包含 `name` 和 `description`，后接 Markdown 指令正文：

```yaml
---
name: readable-code
description: Apply clear, readable, pragmatic design principles when generating, modifying, or reviewing code.
---
```

## 安装位置

将技能文件安装到以下任一位置，并保留 `readable-code/SKILL.md` 目录结构：

- **项目级**：`<repository>/.agents/skills/readable-code/SKILL.md`
- **用户级**：`~/.agents/skills/readable-code/SKILL.md`

## 使用方法

1. 将本目录中的 Codex 版 `SKILL.md` 复制到适合的 Codex skills 目录，创建 `readable-code/` 子目录。
2. 在项目级安装时，技能仅随该项目使用；用户级安装则用于个人环境中的多个项目。
3. 在 Codex 中进行代码生成、修改、重构或审查。可通过 `$readable-code` 显式调用；若当前 Codex 环境支持技能自动选择，也可让 Codex 根据 `description` 匹配。

例如，从仓库根目录执行项目级安装：

```sh
mkdir -p .agents/skills/readable-code
cp skill_for_codex/SKILL.md .agents/skills/readable-code/SKILL.md
```

> Codex 对技能发现与调用的支持可能随产品版本和运行环境变化。若技能未被识别，请检查当前 Codex 文档、路径和重载要求。
