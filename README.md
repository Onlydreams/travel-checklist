# Travel Checklist Skill

A portable travel packing and pre-departure checklist skill. The runtime entrypoint is `skills/travel-checklist/SKILL.md`, which can be read by agents or tools that support the `SKILL.md` convention.

For the Chinese version, see `README_CN.md`.

## Structure

```text
travel-checklist/
├── README.md
├── README_CN.md
├── LICENSE
└── skills/
    └── travel-checklist/
        ├── SKILL.md
        └── references/
            ├── high-risk-outdoor.md
            └── rule-sensitive-checks.md
```

## Usage

Copy or link the complete `skills/travel-checklist` directory into the target agent's supported skills directory. Preserve the `references/` directory; high-risk outdoor and rule-sensitive requests depend on it.

## Upload Targets

Different tools may expect different upload paths or package shapes:

| Target | Use this path or package |
| --- | --- |
| ClawHub single skill publish | `skills/travel-checklist` |
| Skills catalog repository | repository root |
| Claude Code local skill | copy `skills/travel-checklist` to `~/.claude/skills/travel-checklist` |
| Claude Desktop / Claude.ai upload | zip the complete `travel-checklist/` directory, including `SKILL.md` and `references/` |
| OpenClaw local install | copy or install `skills/travel-checklist` so `SKILL.md` is at the skill root |

Packaging details can change between tools. Before publishing, verify the target platform's current packaging requirements. The core compatibility rule is that `SKILL.md` must be at the skill root.

## License

This repository is available under [MIT-0](LICENSE).

## Example Prompts

- What should I pack for a one-week trip to Japan?
- Make me a checklist for a seven-day trip to Yili, Xinjiang.
- I am taking my child to Shanghai Disneyland for a weekend. What should I bring?
- I am going skiing in Hokkaido for five days with carry-on only. How should I pack?
- I am taking my parents to Sanya for a week. What should we prepare?
- I plan to climb Haba Snow Mountain in Yunnan. What should I bring?
- I plan to hike the Wusun Ancient Trail. What should I prepare?
- I am taking my 3-year-old child to Singapore for five days with carry-on only. How should I pack?
- I am taking older adults to Tibet for ten days. Make me a checklist.

## Compatibility

This repository is not tied to a specific agent. `SKILL.md` uses only generic frontmatter:

```yaml
---
name: travel-checklist
description: ...
---
```

The core skill does not depend on Codex, OpenAI, Claude, OpenClaw, Hermes, or vendor-specific metadata. If a specific agent requires extra configuration files, place them in a separate adapter directory or generate them during installation instead of making the core skill depend on them.
