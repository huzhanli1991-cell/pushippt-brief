# Confirmed Production Workflow

Use this reference only after the final planning brief and page production table have been saved locally and the user confirms production.

PushiPPT hard rule: page images must be generated directly with imagegen. Do not stop at writing prompts, do not use another image generator, and do not create text-free slide backgrounds. Each confirmed page image must include the confirmed title, core conclusion, necessary labels, and necessary chart/table text rendered into the image. Do not render page numbers, logos, watermarks, or footers into the images. Optimize for final visual effect, hierarchy, and readability; do not over-constrain layout or wording unless specific facts must be exact. After all images are generated, insert them into an image-version PPTX in content order, then write the complete speaker manuscript and save it as `完整讲稿.md`.

## 0. Usage Mode And Text Density

Before page copy or image production, confirm whether the PPT is for self-reading or live speaking.

- Self-reading deck: allow more on-page text and complete sentences, but split them into short blocks, cards, captions, or bullets.
- Speaking deck: use fewer words, larger type, and short cue phrases; put explanations in `完整讲稿.md`.
- Both modes: never use large paragraphs on a page. If a page needs a paragraph to explain itself, rewrite it into smaller visual units or move detail into speaker notes.

## 0.5 Source Research And Citation

Before content production, proactively search relevant public webpages, reports, datasets, policy pages, product pages, or comparable cases when the user's materials are incomplete or when the topic benefits from current context.

Create or update `资料来源表.md` with:

```text
source id / title / publisher or organization / URL / publish or update date / access date / supported claim or page / reliability note
```

Rules:

- Prefer official, primary, reputable, or clearly attributable sources.
- Use web information only when its origin is clear and the supported claim is traceable.
- Mark uncertain, old, or partially relevant sources as risk instead of treating them as proof.
- Do not use unsourced reposts, unattributed screenshots, fake citations, or unverifiable data.
- If web access is unavailable, say source collection is blocked and ask for user-provided files or links.

## 1. Production Confirmation

Before imagegen, show a compact confirmation:

- saved planning brief path
- saved page production table path
- confirmed page count
- selected style
- usage mode: self-reading or live speaking
- delivery shape
- image-version PPTX output path
- output aspect ratio, default `16:9`
- whether every planned page should become one image
- text/data strategy: all approved page text must be rendered in-image; note separately if a later editable reconstruction may be needed
- whether to generate the complete manuscript and review files after images

Ask for confirmation and stop.

## 2. Page Production Package

Create or update:

```text
00_source/
  PPT制作策划案.md
  资料来源表.md
01_page_specs/
  页面生产表.md
  manifest.json
02_prompts/
  global_style_prompt.md
  slide_01.md ...
03_images/
  slide_01.png ...
04_pptx/
  图片版PPTX.pptx
05_notes/
  QA_checklist.md
  revision_log.md
```

The page production table must include:

```text
page / page type / page purpose / usage mode / text density / page title / required in-image content / must-keep facts / main visual / product consistency / design freedom / delivery shape / risk
```

The table must list the information imagegen must communicate:

- page title
- body copy strategy based on usage mode: denser short blocks for self-reading, lighter and larger cue text for speaking
- labels, source notes, and key chart/table text
- data values only when supplied by Excel/chart screenshot/explicit user-provided values
- exact text only for proper nouns, data values, chart labels, quotations, legal wording, or user-approved sentences that must not change
- image exclusion rule: no page numbers, logos, watermarks, or footers
- product consistency requirement when product images/interfaces/devices appear
- pages that may later require editable reconstruction, without changing the required in-image generation step

## 3. Global Style Prompt And Anchor Pages

Write `global_style_prompt.md` before per-page prompts. It should lock only:

- topic, audience, scenario
- usage mode and expected text density
- chosen style name and visual traits
- color/material/light rules
- mandatory in-image text strategy
- forbidden visual habits
- data/source constraints
- no page number, logo, watermark, or footer rule
- product consistency rule when product visuals appear

Do not over-specify exact layout unless the page must be fixed. The global prompt should explicitly allow imagegen to choose a stronger composition, reorganize content into suitable cards/diagrams/visual scenes, and generate appropriate supporting illustrations when they improve comprehension.

When possible, generate 1-2 anchor pages before the full batch:

- cover page: tests overall tone and title treatment
- dense content or data page: tests information capacity and chart/text readability

If an anchor page drifts from the chosen style, correct it before generating the rest.

## 4. Per-Page Imagegen Prompt Construction

For each page, build a short page-specific instruction containing:

- deck title
- page order for production only; explicitly do not render page numbers
- page type
- usage mode and text density
- core judgment
- page title or must-keep title meaning
- content that must be communicated in the image
- must-keep exact facts: data values, proper nouns, chart labels, quotations, legal wording, or user-approved sentences
- suggested visual object, chart, diagram, or scene, with permission for imagegen to improve the design if it fits the page better
- product consistency requirements if a product, UI, package, device, or mascot appears
- inner title consistency reminder, or cover title special-beauty instruction
- style consistency reminder
- critical exclusions: no page numbers, no logos, no watermarks, no footers, no fake data, no speaker notes, no unsupported claims

Prefer concise prompts that lock judgment, meaning, must-keep facts, and boundaries. Let the model handle composition, content grouping, visual emphasis, and illustration unless the page must follow a fixed layout.

For the cover, add a specific instruction to create a special beautified Chinese title treatment with stronger typography and visual impact than inner pages. For data pages, include the data source or exact values and require post-generation checking. If data is missing, mark the page as blocked for image generation rather than inventing chart text.

## 5. Page Image Rules

Generate exactly the confirmed number of page images with imagegen unless the user confirms anchor-only testing first.

Hard requirements:

- Keep the same canvas ratio and visual system across all pages.
- Prioritize visual effect, information hierarchy, and readability over mechanically following a rigid layout.
- Keep title size, position, and hierarchy consistent on inner pages.
- Give the cover's main title special beautified treatment; it should be visually stronger than inner-page titles.
- Do not place speaker notes or process instructions on the image.
- Do not render page numbers, logos, watermarks, or footers.
- Do not invent text, numbers, product UI, or customer facts.
- If a product appears, keep it consistent across pages in shape, color, interface style, camera-angle family, and distinctive details.
- Ensure required Chinese text is rendered into the image clearly and without garbling.
- Do not let text overlap with decorative graphics, icons, or charts.
- Do not use large paragraphs. Split dense content into compact cards, callouts, comparison blocks, flow steps, or diagrams.
- Make the cover visually stronger than inner pages with special title treatment.

Preferred slide spec:

- 16:9 canvas, preferably 1920x1080 or equivalent.
- Inner-page title: one fixed position across the deck.
- Self-reading body copy: complete sentences are allowed, but keep them short and grouped into compact blocks.
- Speaking body copy: fewer words, larger type, and 3-5 cue phrases or short bullets.

## 6. Quality Check And Regeneration

After each generated image, inspect it before continuing when possible. Regenerate a page if any of these issues appear:

- any page number, logo, watermark, or footer appears
- wrong title text or title drift
- inner-page title size or position drifts without reason
- cover title is too plain or looks the same as an inner-page title
- unreadable, garbled, or hallucinated Chinese text
- speaker notes accidentally placed on the page
- visual style clearly differs from the anchor pages
- text overlaps or is clipped
- page becomes a large paragraph or text density conflicts with the confirmed self-reading/speaking mode
- data or chart values are invented or inconsistent
- product visual changes inconsistently across pages
- AI visual implies a false customer capability, scene, device, or product
- cover lacks distinct title treatment

If exact Chinese text repeatedly fails after reasonable retries, say so plainly, list the affected pages, and still save the best available image attempts in order. Recommend a later deterministic text-layout or editable reconstruction pass as a separate follow-up, but do not skip the required imagegen image production package.

## 7. Create Image-Version PPTX

After all confirmed page images are generated and ordered, create an image-version PPTX:

- Use one full-page image per slide.
- Preserve content order exactly: `slide_01.png` becomes slide 1, `slide_02.png` becomes slide 2, and so on.
- Use the confirmed aspect ratio, default `16:9`.
- Place each image full-bleed without stretching, cropping important text, or adding extra text boxes.
- Save as `04_pptx/图片版PPTX.pptx` or the project-specific equivalent.
- State clearly in delivery notes that this PPTX is an image-version file; page text is not broadly editable.

If the environment lacks a working PPTX library or PowerPoint automation, save the ordered image list and say the PPTX packaging step is blocked by local tooling. Do not claim the PPTX exists until it has been created and opened or structurally verified.

## 8. Complete Speaker Manuscript

After all confirmed page images are generated, create and save `完整讲稿.md`. Do not write the final manuscript before image generation is complete, because the manuscript should reflect the final page order, page titles, and any image-generation risk notes.

Rules:

- Use the approved slide script and speaker notes as the source.
- Write a complete spoken manuscript, not only structured notes, unless the user explicitly asks for notes instead.
- Organize by page: `## 第 X 页：<页面标题>`.
- Include smooth transitions between pages.
- Keep wording aligned with audience, formality, and scenario.
- Do not add claims that are not in the planning brief unless marked as `需确认`.
- Preserve risk notes when evidence is missing.

Suggested structure:

```markdown
## 第 X 页：<页面标题>
<完整口播内容或讲者备注>

过渡：<通向下一页的一句话>
```

## 9. Review And Delivery Files

After images and manuscript, load `review-delivery-workflow.md` and create:

- `审稿清单.md`
- `答辩问题与备用页建议.md`
- `交付清单.md`

The final response must list:

1. Planning brief path.
2. Page production table path.
3. Generated page image paths or attachment list in page order.
4. Image-version PPTX path.
5. Prompt/manifest paths.
6. Manuscript path.
7. Review and delivery checklist paths.
8. Known risks or pages needing manual correction.
