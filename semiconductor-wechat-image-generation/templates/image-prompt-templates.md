# Image Generation Prompt Templates

这些是结构模板，不是可直接重复使用的固定内容。每次必须从当前 Markdown 提取真实章节内容并填充，禁止将同一正文提示词原样用于多个章节。

## 1. Cover

Create ONE standalone WeChat public-account cover for the exact article title: {ARTICLE_TITLE}.

- Target: 2350 × 1000 px, 2.35:1.
- Use the approved blue-and-white semiconductor engineering visual style.
- Main subject: {ARTICLE_MAIN_SUBJECT}.
- Core engineering question: {ARTICLE_CORE_QUESTION}.
- Relevant hardware / test scene: {RELEVANT_HARDWARE}.
- Keep the title and main subject inside the WeChat crop-safe area.
- Cover only: no chapter numbers, chapter panels, multi-section summary, or body-page Takeaway.
- Exactly one image; no collage, grid, montage, or contact sheet.

## 2. Intro

Create ONE standalone intro infographic for this exact Markdown heading: {INTRO_HEADING}.

- Target: 1573 × 1000 px.
- Follow the approved visual master: left-aligned deep-blue heading, consistent typography, clear engineering panels, relevant equipment, and bottom Takeaway.
- Show only the intro's source-grounded context, field symptoms, problem statement, and diagnostic question: {INTRO_CONTENT_MAP}.
- Do not use the article title as the page title.
- Exactly one image; no collage or multi-chapter content.

## 3. Body chapter

Create ONE standalone blue-and-white engineering infographic for this exact original Markdown heading: {EXACT_CHAPTER_HEADING}.

- Target: 1573 × 1000 px.
- Match the approved visual master, including title typography, left alignment, title-bar placement, palette, card borders, arrows, and bottom Takeaway.
- This is a body page, NOT a cover. Do not use the article title as the main heading.
- Cover only this chapter: {CHAPTER_CORE_MESSAGE}.
- Exact logic / flow and direction: {EXACT_FLOW}.
- Required formulas, parameters, units, and conditions: {FORMULAS_AND_CONDITIONS}.
- Relevant DUT / hardware / tester / waveform / chart: {VISUAL_ELEMENTS}.
- Important subsection points: {SUBSECTION_POINTS}.
- Source-grounded chapter Takeaway: {CHAPTER_TAKEAWAY}.
- Do not invent numeric data, standards, vendor specifications, or test results. Label schematic data as illustrative.
- Do not include other chapter headings or content.
- Exactly one independent image; no collage, grid, montage, storyboard, or contact sheet.

## 4. Summary

Create ONE standalone summary infographic for the exact summary heading: {SUMMARY_HEADING}.

- Target: 1573 × 1000 px.
- Match the approved blue-and-white engineering visual master and unified left-aligned heading.
- Summarize only conclusions and recommendations supported by the complete Markdown: {SOURCE_GROUNDED_SUMMARY}.
- Use a compact engineering logic map or checklist and a deep-blue final Takeaway.
- No unsupported claims or invented data.
- Exactly one image; no collage or multi-page montage.
