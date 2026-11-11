# AI_Skills

A dedicated repository for reusable Agent Skills used across the user's AI workflows.

## Default Skill storage policy

**All new and updated Skills must be stored in this repository by default.** Do not create new Skill libraries inside individual project repositories unless the user explicitly requests a project-local copy.

## Repository structure

Each Skill lives in its own top-level directory:

~~~text
AI_Skills/
├── README.md
├── semiconductor-wechat-image-generation/
│   ├── SKILL.md
│   ├── README.md
│   ├── references/
│   └── templates/
└── <future-skill-name>/
    ├── SKILL.md
    ├── references/
    └── templates/
~~~

## Skill authoring conventions

1. Each Skill must have a root `SKILL.md` with YAML frontmatter containing `name` and `description`.
2. Put canonical policies, specifications, and domain references in `references/`.
3. Put reusable checklists, manifests, and prompt structures in `templates/`.
4. Keep each Skill self-contained and use relative links to its supporting files.
5. Use lowercase kebab-case directory names matching the Skill name.
6. Include version and change notes in the Skill README when useful.
7. Do not store article-specific deliverables or generated image outputs in this repository.
8. Before creating a new Skill, inspect this repository for an existing Skill that should be extended instead.
9. After changes, verify every referenced file and relative path.
10. When migrating a Skill, copy and verify the destination first; only then remove the old project-local copy and update links.

## Available Skills

| Skill | Purpose | Entry |
|---|---|---|
| Semiconductor WeChat Image Generation | Generate one independent WeChat cover, intro, chapter, and summary image per planned content unit from semiconductor engineering Markdown. | [SKILL.md](semiconductor-wechat-image-generation/SKILL.md) |
| WeChat Article Formatting | 将 Markdown 转为公众号富文本 HTML，保留公式排版，统一标题、表格和箭头间距。 | [SKILL.md](wechat-article-formatting/SKILL.md) |
| HTRB&HTGB OS DRC | 核对工装 PCB 与 DXF 的孔位和板框，检查铜箔干涉及明显开短路，支持修正版复查。 | [SKILL.md](htrb-htgb-os-drc/SKILL.md) |

## Change log

- 2026-11-05: Added WeChat Article Formatting Skill.

- 2026-11-04: Created the independent Skill library and migrated the Semiconductor WeChat Image Generation Skill (V1.1).
