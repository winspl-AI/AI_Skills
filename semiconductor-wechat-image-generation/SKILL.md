---
name: semiconductor-wechat-image-generation
description: Generate, continue, revise, quality-check, and package complete WeChat image sets from semiconductor and engineering Markdown articles, including ATE, SiC/IGBT, Probe Card, Test Socket, reliability, and power-device topics.
---

# Semiconductor WeChat Image Generation

## Mission
Turn one formal Markdown article into a complete WeChat public-account image set. The Markdown is the content source. The current-turn reference image and previously approved pages from the same article define the visual master. Generate one independent image for every planned cover, eligible intro, major chapter, and summary.

## Mandatory reading
Before production, read the complete canonical specification at:
- references/wechat-image-rules-v1.1.md

Use these templates:
- templates/image-task-manifest.md
- templates/image-prompt-templates.md
- templates/image-qc-checklist.md

The user's latest approved instructions and the canonical reference are authoritative. Do not silently reconcile ambiguity or replace source terminology with generic knowledge.

## When to use
Use when the user provides or references a Markdown article and asks to generate all WeChat images, continue remaining chapters, regenerate missing/incorrect images, apply historical/latest image rules, check image quality, or package the deliverables.

## Required inputs
- Formal Markdown article.
- Current visual reference image(s), if supplied.
- Approved earlier images from the same article, if available.

Do not ask the user to repeat information already available. If the Markdown cannot be read, request it rather than guessing.

## Workflow

### 1. Parse the complete Markdown
1. Read the entire article.
2. Record the article title and every heading in original order.
3. Normally treat level-two headings (##) as major-section candidates; integrate level-three and lower headings into their parent.
4. Generate a standalone intro image when 导语 or equivalent is a standalone level-two section, unless explicitly excluded.
5. Generate one standalone summary image.
6. Do not normally create a separate image for references/bibliography.
7. Follow explicit article-specific structure or exclusions.

### 2. Build the manifest before generation
Use templates/image-task-manifest.md. For every planned image record:
- sequence and type: cover / intro / chapter / summary;
- exact original Markdown heading;
- source subsections covered;
- chapter-specific core message;
- essential formulas, parameters, units, conditions, flows, and diagrams;
- filename, target dimensions, batch, generation status, and QC status.

Calculate the total from the actual Markdown:
1 cover + eligible intro + each eligible major chapter + 1 summary.
Show the full manifest before generating. Never silently skip, merge, or duplicate a chapter.

### 3. Lock the visual master
Visual reference priority:
1. Explicit reference image in the current request.
2. Approved earlier images from the same article.
3. Other user-approved historical images.
4. Canonical V1.1 specification.

Use the approved blue-and-white, high-information-density semiconductor engineering infographic style. Keep body/summary title typography, left alignment, title-bar position, palette, card borders, arrows, and bottom Takeaway consistent. Let each chapter's content determine its internal layout.

Do not introduce a new style or template without approval. Do not use Adobe as a substitute for the approved image-generation workflow.

### 4. Generate one image at a time
Use the available image-generation model/tool. Each generation request must create exactly one image for exactly one manifest item.

- Cover: one cover only.
- Intro: one intro only, if included.
- Each major chapter: one image showing only that chapter.
- Summary: one summary only.

Never request a collage, grid, montage, contact sheet, storyboard, or multi-chapter sheet. Never crop a collage into chapter images. Never reuse one image with a changed heading to represent another chapter.

Before each generation, build a chapter-specific prompt from that Markdown section: exact heading, unique topic, core logic, formulas/parameters, visual objects, and source-grounded Takeaway. For body pages, explicitly prohibit cover composition, article-title substitution, and unrelated chapter content.

Reject any collage, wrong chapter, repeated chapter, or cover-style image returned for a body page. Do not count or deliver it. Mark it 待返工 and retry with a more specific prompt. Never claim an image exists unless an actual image output exists.

### 5. Dimensions
- Cover: 2350 × 1000 px, 2.35:1, PNG.
- Intro/body/summary: 1573 × 1000 px, about 1.573:1, PNG.

Verify actual pixel dimensions. If resizing is required, preserve aspect ratio and all important content. Never stretch, squash, or crop key information. Post-processing must not replace independent generation.

### 6. Quality control
Use templates/image-qc-checklist.md for every image.

Content: exact heading; only assigned-section content; source-grounded logic; correct formulas, units, values, conditions, and flow direction; no cross-chapter mixing; no invented data, standards, vendor specifications, or experimental results. Label illustrative data/curves as examples.

Visual: approved blue/white engineering style; consistent left-aligned body title; relevant hardware; readable text; no severe garbling, clipping, overlap, or misleading labels; Takeaway summarizes only the current section; no article-cover headline on body pages.

File: PNG, correct dimensions, chapter-based filename, one file per manifest item, no collage/duplicate/draft/rejected output in final folders.

A professional-looking image that does not match its assigned chapter is a failure. Content accuracy outranks decoration.

### 7. Naming and folders
Use the exact original Markdown heading as each body filename. Do not paraphrase or shorten it. If a filesystem forbids a character, make only the minimum safe substitution and preserve the exact source heading in the manifest.

- Cover: 封面_<文章正式标题>.png
- Intro: 导语.png or exact original intro heading
- Body: <原始章节标题>.png
- Summary: 总结.png if the source heading is simply 总结; otherwise use the exact source heading.

Recommended structure:
~~~text
公众号配图交付包_<文章名称>/
├── 01_封面/
├── 02_正文配图/
├── 03_总结/
├── 04_验收清单/
└── 05_最终压缩包/
~~~

Keep drafts and rejected images outside formal delivery folders.

### 8. Batches and continuation
If all images cannot be generated in one run, split into batches. Batching changes only delivery order, never generation method, content, dimensions, naming, or style. Track planned, generated, accepted, rejected, and remaining images.

When the user says 继续, resume from the first 待生成 or 待返工 item. Do not restart from the cover or regenerate accepted images unless requested or QC finds a real defect. Use accepted earlier pages as the visual master for later batches.

### 9. Package and deliver
Only accepted images enter the final package. Include final PNGs, task manifest, and QC report. Verify the ZIP exists, opens, contains the expected count and filenames, and contains no drafts or invalid collages. Provide the actual download link. Never invent a sandbox path or claim verification without evidence.

## Reporting
- First report parsed count and full task manifest.
- Generate in article order, one image at a time or in tracked batches.
- Send valid images as they are produced when incremental delivery is expected.
- Never send a progress update instead of the requested image.
- Identify invalid outputs and retry; do not mark them complete.
- Never claim saved, uploaded, packaged, or verified unless that action succeeded.

## Completion criteria
Complete only when every planned item is 验收通过, accepted count equals manifest count, filenames and dimensions are verified, and the ZIP is verified. If any item is missing or rejected, report the exact outstanding items and do not call the set complete.
