# 旅行检查清单技能

这是一个通用的旅行打包与出门前检查清单技能。核心运行入口是 `skills/travel-checklist/SKILL.md`，支持 `SKILL.md` 约定的智能体或工具都可以读取。

英文版本见 `README.md`。

## 目录结构

```text
travel-checklist/
├── README.md
├── README_CN.md
└── skills/
    └── travel-checklist/
        ├── SKILL.md
        └── references/
            └── high-risk-outdoor.md
```

## 使用方式

把 `skills/travel-checklist` 复制或链接到目标智能体支持的技能目录中。

## 上传目标

不同工具对上传目录或压缩包结构的要求可能不同：

| 目标 | 使用路径或打包方式 |
| --- | --- |
| ClawHub 单技能发布 | `skills/travel-checklist` |
| 技能目录仓库 | 仓库根目录 |
| Claude Code 本地技能 | 把 `skills/travel-checklist` 复制到 `~/.claude/skills/travel-checklist` |
| Claude Desktop / Claude.ai 上传 | 压缩包内包含 `travel-checklist/SKILL.md` |
| OpenClaw 本地安装 | 复制或安装 `skills/travel-checklist`，确保 `SKILL.md` 位于技能根目录 |

具体打包要求可能随工具版本变化。发布前应以目标平台当前要求为准。核心兼容规则是：`SKILL.md` 必须位于技能根目录。

## 示例提问

- 我要去国外日本旅游一周，需要带什么？
- 我要去新疆伊犁旅游七天，给我生成检查清单。
- 我要带孩子去上海迪士尼玩一个周末，帮我看看带什么东西？
- 我要去北海道滑雪五天，只带登机箱，怎么打包？
- 我要带老人去三亚住一周，需要准备什么？
- 我打算去云南爬哈巴雪山，需要带些什么？
- 我打算去走乌孙古道，需要准备什么？
- 我带 3 岁孩子去新加坡玩 5 天，只带登机箱，怎么打包？
- 我带老人去西藏旅行 10 天，需要检查清单。

## 兼容性

本仓库不绑定特定智能体。`SKILL.md` 只使用通用 frontmatter：

```yaml
---
name: travel-checklist
description: ...
---
```

核心技能不依赖 Codex、OpenAI、Claude、OpenClaw、Hermes 或其他特定厂商的元数据。如果某个智能体需要额外配置文件，建议放在独立 adapter 目录，或由安装流程生成，不要让核心技能依赖这些配置。
