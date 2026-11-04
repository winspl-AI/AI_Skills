# Semiconductor WeChat Image Generation

Version: 1.1.0  
Canonical specification: 微信公众号技术文章配图生成规则 V1.1（完整执行版）

## Package contents

- SKILL.md — Skill metadata, triggers, workflow, and completion criteria.
- references/wechat-image-rules-v1.1.md — exact copy of the approved V1.1 image-generation rules.
- templates/image-task-manifest.md — image planning and progress tracking.
- templates/image-prompt-templates.md — cover, intro, body, and summary prompt structures.
- templates/image-qc-checklist.md — per-image and final-package quality checks.

## How to invoke

Use this Skill for a formal Markdown article. Example request:

“Use semiconductor-wechat-image-generation to generate all WeChat images for this Markdown.”

The Skill must parse the complete Markdown, show the full task manifest, lock the visual master, generate one independent image per request, validate every image, and package only accepted outputs.

## Runtime requirements

This repository stores the Skill source; it does not automatically install the Skill into Codex, ChatGPT, or another agent runtime. The runtime must support loading SKILL.md and provide an image-generation capability. If that capability is unavailable, the agent must state the limitation rather than fabricate outputs or mark images complete.

## Versioning

When the user approves a new image-rule revision:
1. Preserve prior approved references when historical traceability is required.
2. Add the new canonical rule file under references/.
3. Update SKILL.md and templates only where the new rule requires it.
4. Update this README version and revision notes.
5. Verify that all references resolve.
