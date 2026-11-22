# readable-code-skill

面向多种 AI 编码工具的代码生成与审查技能集合。核心原则是：清晰、简洁、可读、一致、务实，并在必要时进行验证。

## 仓库结构

```text
skill_for_claude/
  SKILL.md
skill_for_codex/
  SKILL.md
README.md
```

## Claude

Claude 的自定义 Skill 为一个目录，目录中必须包含 `SKILL.md`，并可包含可选的 `scripts/`、`references/`、`assets/` 或 `LICENSE.txt`。

```text
readable-code/
└── SKILL.md
```

`SKILL.md` 顶部需要 YAML frontmatter：

```yaml
---
name: readable-code
description: Apply clear, readable, pragmatic design principles when generating, modifying, or reviewing code.
---
```

保存方法取决于 Claude 使用环境，通常使用 Claude 提供的 Skills、Projects、Team 或个人上传入口；上传时选择包含 `SKILL.md` 的技能目录。具体保存位置由对应 Claude 产品界面或管理设置决定，不应假设为仓库中的固定目录。

Claude 适配文件位于：

```text
skill_for_claude/SKILL.md
```

## Codex

Codex 会从用户级和项目级的 `.agents/skills/` 目录发现 Skill。每个 Skill 使用独立目录，目录内必须包含 `SKILL.md`。

项目级安装：

```text
<repository>/.agents/skills/readable-code/SKILL.md
```

用户级安装：

```text
~/.agents/skills/readable-code/SKILL.md
```

每个目录中的 `SKILL.md` 顶部需要：

```yaml
---
name: readable-code
description: Apply clear, readable, pragmatic design principles when generating, modifying, or reviewing code.
---
```

Codex 可通过 `$readable-code` 调用，或根据描述自动选择技能。可选目录包括 `references/`、`scripts/` 和 `assets/`；本技能目前不需要这些目录。

Codex 适配文件位于：

```text
skill_for_codex/SKILL.md
```

安装时将该文件复制到上述任一 Codex Skills 目录，并保持目录结构：

```text
.agents/skills/readable-code/SKILL.md
```

或：

```text
~/.agents/skills/readable-code/SKILL.md
```

## 技能核心规则

- 优先清晰、简洁、可读和易于解释。
- 在动手前理解需求与约束；遇到影响实现的歧义时不要擅自猜测。
- 特例必须有充分理由；遵循项目约定与用户明确要求。
- 实用��高于理论上的纯粹性，但不能以牺牲必要验证为代价。
- 不要隐藏错误；只有明确允许时才忽略错误。
- 优先扁平、直接的实现；在复杂度确有必要时组织好职责边界。
- 合理使用命名空间和模块，只在它们确实解决实际问题时拆分。
- 修改后执行相关测试、检查或构建；无法验证时明确说明。

## 使用方式

1. 根据目标工具选择相应目录中的 `SKILL.md`。
2. 按本 README 中的保存位置放置文件。
3. 在代码生成、重构或代码审查任务中调用或加载该技能。
4. 若工具支持自动匹配，描述应使它能识别“代码生成、代码审查、重构、可读性”等场景。

## 后续适配

后续添加新的工具时，建议新建 `skill_for_<tool_name>/` 目录，并在 README 中说明：

- 必需目录结构
- `SKILL.md` 或等价配置格式
- 用户级保存位置
- 项目级保存位置
- 是否支持脚本、资源或附加引用文件
- 调用方式及自动加载规则
