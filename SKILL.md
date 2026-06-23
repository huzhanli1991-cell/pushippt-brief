---
name: pushippt-brief
description: >-
  Generate a complete PPT production planning brief and required page-image
  production package from a presentation request using the bundled 10-chapter
  AI-PPT course-derived workflow references: task diagnosis,
  source-backed web research, materials package, persuasive mainline, slide-by-slide script, page copy,
  visual system, data-page planning, asset planning, GPT Image 2/Codex page-image
  production with imagegen, required in-image text rendering, image-version PPTX packaging,
  delivery-shape decision, five-round review, speaker/defense prep,
  and final delivery checklist. Use when the user wants a PPT strategy document,
  production brief, planning proposal, page script, content blueprint, style
  recommendation, page images, AI PPT image workflow, review checklist, complete
  manuscript, delivery package, or three-part PPT production workflow.
---

# PushiPPT Brief

## Purpose

Create a complete `PPT制作策划案` before visual production. The course-derived workflow is bundled inside this skill under `references/`, so normal use does not require reading the original course folder.

The skill follows the course as a gated workflow:

1. Chapters 1-8: diagnose the task, organize materials, build the mainline, write slide scripts and page copy, define visual/data/asset plans.
2. Chapter 9: turn the approved brief into a page production table and decide the correct delivery shape before generating images.
3. Chapter 10: review the draft with five rounds of checks, prepare speaker/defense support, and package the final handoff clearly.

Use the bundled curated style library by default:

```text
references/PPT制作风格库.md
```

## Scope

The final package can include:

- `PPT制作策划案.md`
- `资料来源表.md`
- `页面生产表.md`
- page-image prompts and imagegen-generated page images with on-page text rendered into the images
- image-version PPTX created by inserting the generated page images in content order
- `完整讲稿.md`
- `审稿清单.md`
- `答辩问题与备用页建议.md`
- `交付清单.md`

This skill creates an image-version PPTX by placing each generated full-page image on its own slide in content order. It still does not promise editable PPTX/source reconstruction unless the user explicitly asks for a separate reconstruction workflow.

## Core Output-Mode Rules

Before writing page content, ask whether the PPT is mainly for self-reading or for live speaking.

- **Self-reading deck**: page text can be denser and may use complete sentences so the reader can understand the content without narration.
- **Speaking deck**: page text should be lighter, larger, and closer to cue phrases, keywords, or short bullets because the explanation belongs in the manuscript.
- **Both modes**: never put large paragraphs on slides. Split long explanations into short blocks, cards, bullets, diagrams, or speaker manuscript.

During imagegen production, optimize first for visual effect, hierarchy, and readability. The prompt should provide the page intent, required meaning, must-keep facts, and style direction, while leaving imagegen room to organize wording, layout, illustration, and composition. Lock exact text only for proper nouns, data values, chart labels, quotations, legal wording, or user-approved sentences that must not change.

## Source Research Rules

When creating content, proactively search the web for relevant public webpages, reports, statistics, product information, policy context, market references, or comparable cases that can help the user fill gaps.

- Use reliable, attributable sources: official sites, public reports, reputable media, standards/policy pages, company documentation, dataset pages, or clearly identified primary sources.
- Record source title, publisher/organization, URL, publish/update date when available, access date, and which claim/page it supports.
- Separate user-provided material, verified web material, and unsupported assumptions.
- Do not use information with unclear origin, unattributed reposts, unverifiable screenshots, invented citations, or outdated data without date/risk notes.
- If web access is unavailable, state that source collection is blocked and ask the user to provide source files or links; do not pretend to have verified sources.

## Image Layout Rules

Generated slide images must not include page numbers, logos, watermarks, footers, or decorative brand marks unless the user explicitly overrides this rule for a supplied official asset. Keep page order only in filenames, manifest, and PPTX slide order.

- If product visuals appear, maintain product consistency across pages: same shape, color, interface style, camera angle family, and distinctive details unless a page intentionally compares variants.
- Inner-page titles should keep size, position, and hierarchy as consistent as the selected style allows.
- Cover title should receive special beautified treatment: stronger typography, more expressive composition, and higher visual impact than inner pages.

## Non-Goals

- Do not generate page images before the planning brief and page production table are saved and confirmed.
- Do not use non-imagegen image generation for the core page images. After Gate J confirmation, call imagegen directly for each confirmed page.
- Do not produce text-free slide images. The confirmed title, core conclusion, necessary labels, and required chart/table text must be rendered into each generated image, but do not over-lock layout or wording when design freedom improves the page.
- Do not render page numbers, logos, watermarks, or footers into generated images.
- Do not treat AI-rendered text or data inside images as editable content. If the user later needs editable text, handle that as a separate semi-editable or full editable reconstruction workflow after the image package is complete.
- Do not invent data, sources, customer names, case permissions, policy validity, product appearance, or chart numbers.
- Do not search the broad raw style folder unless the curated style file is missing or the user explicitly asks.
- Do not promise editable PPTX/source reconstruction by default. Image-version PPTX packaging is required after page images are generated; editable reconstruction remains a later optional workflow.

## Mandatory Human Gates

Ask concise questions at key nodes and stop after each gate. Do not continue until the user answers or explicitly says to skip that gate.

- **Gate A, Intake**: Ask for audience, target action, scenario, whether the PPT is for self-reading or live speaking, topic/materials, page count, must-include items, forbidden items, deadline, and expected delivery shape/editability.
- **Gate B, Task Brief**: Present PPT type, audience, current belief, core resistance, target action, success standard, and forbidden writing. Ask for correction.
- **Gate C, Materials**: Present usable evidence, verified web sources, weak evidence, gaps, risky claims, and forbidden expressions. Ask what can be supplied and what should remain marked as risk.
- **Gate D, Mainline**: Present 2-3 narrative options. Ask the user to choose, combine, or reject.
- **Gate E, Page Plan**: Present page list with page task, judgment title, evidence, and visual direction. Ask whether to add, delete, merge, or reorder.
- **Gate F, Style Recommendation**: Read bundled `references/PPT制作风格库.md`, shortlist 3-5 styles with the library's exact fields, recommend one, and ask for confirmation. Tell the user they may also directly choose any style by exact编号 such as `PPT-S86`.
- **Gate G, Delivery Shape**: Recommend one of quick visual draft, image-version PPT, semi-editable draft, or editable/source reconstruction. State clearly that PushiPPT production still renders required page content directly into the image while allowing design-oriented wording/layout organization; editable reconstruction is a later optional workflow.
- **Gate H, Final Brief**: Present the final brief and ask whether to save it as Markdown unless the user already requested saving.
- **Gate I, Page Production Table**: Before image generation, present the page production table: page type, purpose, usage mode, text density, title, required in-image content, must-keep facts, main visual, product consistency requirement, design freedom, text strategy, delivery shape, and risk.
- **Gate J, Production Confirmation**: After saving, summarize paths, page count, style, expected image count, required in-image text strategy, no-page-number/no-logo image rule, PPTX output path, and manuscript/review outputs. Ask for confirmation before imagegen.
- **Gate K, Final Package Review**: After production, PPTX packaging, and review files are generated, present deliverables and known risks. Ask whether to revise images, manuscript tone, delivery shape, or enter editable reconstruction.

For exact wording, load `references/interaction-gates.md`.

## Workflow

Load `references/course-1-10-workflow.md` for the full course-derived workflow.

1. Diagnose the PPT task before writing an outline.
2. Turn raw materials into a usable PPT production package.
   Proactively collect and cite relevant web sources when content needs context, data, product information, or external proof.
3. Generate and choose a persuasive mainline.
4. Convert the mainline into a slide-by-slide script.
5. Rewrite script content into page copy according to the confirmed self-reading or speaking mode.
6. Define the visual system direction.
7. Plan data pages from question to conclusion to chart.
8. Plan visual assets and evidence materials.
9. Recommend a style using `references/style-selection.md`.
10. Decide delivery shape and text/data editability before image production, while preserving the PushiPPT rule that confirmed content must be rendered into the generated images and imagegen should retain design freedom.
11. Create the final planning brief using `references/planning-brief-schema.md`.
12. After confirmation, load `references/production-workflow.md` to build the page production table, imagegen prompts, full-page images with text rendered in-image, image-version PPTX, manifest, and manuscript.
13. Load `references/review-delivery-workflow.md` to run five-round review and prepare the delivery checklist.

## Logic Models

Use `references/logic-models.md` to strengthen reasoning. Apply these in every brief:

- audience-shift-action model
- resistance map
- evidence pyramid
- narrative structure selector
- slide task canvas
- data insight ladder
- asset priority matrix
- delivery-shape decision matrix
- five-round review model

Name the model used in the relevant section so the reasoning is visible.

## Output Behavior

When enough information is available, produce a complete Markdown brief in chat. If the user asks for a file or approves saving at Gate H, save it as:

```text
<workspace or project folder>\PPT制作策划案.md
```

The planning brief must include:

- project overview
- self-reading or speaking mode and page-text density
- source-backed research and `资料来源表.md`
- task diagnosis
- applied logic models
- materials package
- chosen mainline and structure
- slide-by-slide script
- page copy
- visual system direction
- data-page plan
- asset plan
- style recommendation using curated style-library fields
- page production table
- delivery-shape recommendation
- risks and missing evidence
- review and delivery plan
- production handoff checklist

After Gate J confirmation, produce and save the production package. The order is mandatory: first generate all confirmed page images with imagegen, including required page text inside the images; then insert those images into an image-version PPTX in content order; then write the complete speaker manuscript and save it as Markdown.

```text
<workspace or project folder>\PPT制作策划案.md
<workspace or project folder>\资料来源表.md
<workspace or project folder>\页面生产表.md
<workspace or project folder>\prompts\global_style_prompt.md
<workspace or project folder>\prompts\slide_01.md ...
<workspace or project folder>\PPT页面图片\第01页.png ...
<workspace or project folder>\PPT\图片版PPTX.pptx
<workspace or project folder>\完整讲稿.md
<workspace or project folder>\审稿清单.md
<workspace or project folder>\答辩问题与备用页建议.md
<workspace or project folder>\交付清单.md
```

If imagegen returns app attachments rather than direct files, preserve generated order, name each page in the final deliverable list, and save all text artifacts locally.
