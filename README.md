# Travel Checklist Skill

通用旅行出门检查清单 skill。核心运行时文件是 `skills/travel-checklist/SKILL.md`，可被支持 `SKILL.md` 约定的 agent 或工具读取。

## Structure

```text
travel-checklist/
├── README.md
└── skills/
    └── travel-checklist/
        └── SKILL.md
```

## Usage

把 `skills/travel-checklist` 复制或链接到目标 agent 支持的 skills 目录中。

## Upload Targets

不同工具对上传目录的期望不完全一样：

| Target | Use this path or package |
| --- | --- |
| ClawHub single skill publish | `skills/travel-checklist` |
| Skills catalog repository | repository root |
| Claude Code local skill | copy `skills\travel-checklist` to `~\.claude\skills\travel-checklist` |
| Claude Desktop / Claude.ai upload | zip containing `travel-checklist\SKILL.md` |
| OpenClaw local install | copy or install `skills\travel-checklist` so `SKILL.md` is at the skill root |

Packaging details can change between tools. Before publishing, verify the target platform's current packaging requirements. The core compatibility rule is that `SKILL.md` must be at the skill root.

## Example Prompts

- 我要去国外日本旅游一周，需要带什么？
- 我要去新疆伊犁旅游七天，给我生成检查清单。
- 我要带孩子去上海迪士尼玩一个周末，帮我看看带什么东西？
- 我要去北海道滑雪五天，只带登机箱，怎么打包？
- 我要带老人去三亚住一周，需要准备什么？
- 我打算去云南爬哈巴雪山，需要带些什么？
- 我打算去走狼塔C+V，需要带什么？
- 我带3岁孩子去新加坡玩5天，只带登机箱，怎么打包？
- 我带老人去西藏旅行10天，需要检查清单。

## Compatibility

本仓库不绑定特定 agent。`SKILL.md` 只使用通用 frontmatter：

```yaml
---
name: travel-checklist
description: ...
---
```

不依赖 Codex、OpenAI、Claude、OpenClaw、Hermes 或其他特定厂商的 metadata。若某个 agent 需要额外配置文件，建议放在独立 adapter 目录或由安装流程生成，不要让核心 skill 依赖它。
