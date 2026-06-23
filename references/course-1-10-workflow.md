# Course 1-10 Workflow

Use this workflow to create a complete PPT production plan before image generation. Chapters 1-8 create the planning brief. Chapter 9 turns the brief into page-image production instructions and a delivery-shape decision. Chapter 10 reviews and packages the output.

## 1. Task Diagnosis

Goal: decide what the PPT must accomplish.

Output:

- PPT title
- PPT type: report, decision, sales, training, pitch, communication, data, mixed
- target audience
- current audience belief
- desired judgment
- core resistance
- target action
- use scenario
- usage mode: self-reading or live speaking
- success standard
- forbidden writing

Core formula:

```text
我要让【谁】从【当前认知】变成【新的判断】，并采取【下一步动作】。
```

## 2. Materials Package

Goal: organize raw information into usable proof and page materials.

Before building the evidence package, proactively search public webpages, reports, datasets, product pages, policy pages, or comparable cases when they can improve the content. Keep only traceable sources and record them.

Output seven parts:

1. Raw material list: material, source, credibility, public/private, notes.
2. Web source table: source id, title, organization, URL, publish/update date, access date, supported claim/page, reliability note.
3. Information classification table: raw material, type, importance, page use, treatment, risk.
4. Page material pool: page direction, usable material, presentation suggestion.
5. Forbidden-expression table: forbidden phrase, risk, replacement.
6. Gap list: missing data, cases, screenshots, testimonials, authorization, official wording.
7. Initial judgment: what PPT type the materials best support and what must be supplemented next.

Source rules:

- Prefer official, primary, reputable, or clearly attributable sources.
- Do not use source-unclear reposts, unverifiable screenshots, fake citations, or outdated data without risk notes.
- Separate user-provided material from verified web material.
- If web access is blocked, state the blocker and ask the user for source files or links.

Translation rules:

- Sales: translate features into customer problems.
- Report: translate activities into business judgment.
- Training: translate knowledge points into learner actions.
- Pitch: translate big claims into evidence.
- Data: translate charts into conclusions.

## 3. Persuasive Mainline

Goal: build an audience cognition route, not a table of contents.

Generate 2-3 options. Each option includes:

- mainline sentence
- current belief
- desired judgment change
- core contradiction
- recommended structure
- suggested page count
- strength
- risk

Common structures:

- Problem progression: problem -> cost -> solution -> proof -> action
- Conclusion first: conclusion -> evidence -> reason -> risk -> next step
- Task training: goal -> demo -> practice -> formula -> assignment
- Trust building: real problem -> specific solution -> data proof -> team/ability -> next step
- Memory point: one memorable claim -> three scenes/stories -> closing phrase

## 4. Slide-by-Slide Script

Goal: turn the mainline into a producible page plan.

For every page, output:

- page order for planning only; do not render it as a visual page number
- page task
- audience judgment to move
- conclusion title
- body points, max 4
- evidence material
- visual suggestion
- speaker note
- next-page transition

Mark missing evidence as `需补充资料`.

## 5. Page Copy

Goal: turn the script into concise text suitable for PPT pages.

Rules:

- Use conclusion titles, not column labels.
- Confirm self-reading or live speaking mode before deciding text density.
- For self-reading decks, allow complete short sentences and slightly denser content so the page can stand alone.
- For speaking decks, keep body text lighter, larger, and closer to cue phrases.
- In both modes, avoid large paragraphs; split long explanations into bullets, cards, captions, diagrams, or speaker notes.
- Remove empty terms and over-claims.
- Split pages when one page carries multiple judgments.

## 6. Visual System Direction

Goal: define design direction without creating final visuals.

Output:

- style positioning
- color direction
- typography hierarchy
- layout rules
- component rules
- image rules
- product consistency rules
- no page numbers, logos, footers, or watermarks in generated images
- chart rules
- forbidden visual habits

The visual direction must serve the PPT type and audience: credible for sales/consulting, readable for training, judgment-focused for reports, proof-oriented for pitches.

## 7. Data-Page Planning

Goal: plan data pages from insight, not from chart type.

Workflow:

```text
question -> data -> finding -> conclusion -> chart -> annotation -> action
```

For each data page, output:

- question the data should answer
- data source and caliber
- possible findings
- conclusion title
- chart type
- key annotations
- data-caliber checks
- action the page should lead to

Do not let AI invent data. Use Excel, chart screenshots, or explicit values.

## 8. Asset Planning

Goal: decide what visual assets each page needs.

Asset types:

- real screenshot
- data chart
- process diagram
- comparison table
- AI illustration direction
- icon combination
- photo
- no image

Output:

```text
page / page conclusion / recommended asset type / why / what to prepare / risk
```

Rules:

- Sales, pitch, report, consulting: prioritize evidence assets.
- Training: prioritize screenshots, exercise samples, before/after examples.
- Data: prioritize charts and annotated tables.
- Communication/keynote: allow stronger concept or emotion assets, but keep the message clear.

## 9. Page-Image Production And Delivery Shape

Goal: turn chapters 1-8 into executable imagegen page-generation instructions, then choose a delivery shape that matches editability needs.

PushiPPT production rule: after the user confirms production, use imagegen directly to generate every confirmed page image. The confirmed title, core conclusion, necessary labels, and necessary chart/table text must be rendered into the image. Do not add page numbers, logos, footers, or watermarks. Do not default to text-free backgrounds. Optimize for visual effect and readability, and allow imagegen to improve layout, content grouping, and supporting illustration unless must-keep facts require exact wording. If products appear, keep product appearance, UI style, package/device shape, and distinctive details consistent across pages. Inner-page titles should stay consistent in size and position; the cover title should receive special beautified treatment. After all images are generated, create an image-version PPTX in content order, then write the complete speaker manuscript and save it as `完整讲稿.md`.

First ask four delivery questions:

1. Is this PPT mainly for self-reading or live speaking?
2. Is this PPT a one-time display, or will it be repeatedly revised and reused?
3. What is likely to be changed later: text, images, data, brand colors, charts, or structure?
4. Is the deliverable a visual direction draft, an image-version PPT, a semi-editable draft, or a maintainable source file?

Create a page production table:

```text
page / page type / page purpose / usage mode / text density / page title / required in-image content / must-keep facts / main visual / product consistency / design freedom / delivery shape / risk
```

Image text strategy:

- Generation stage must include the required title/core conclusion/label text in the imagegen prompt.
- The prompt should lock only must-keep facts and let imagegen choose better composition, grouping, illustration, and hierarchy.
- The prompt must explicitly forbid page numbers, logos, footers, and watermarks.
- If product visuals appear, include consistency constraints across pages.
- Delivery stage can later rebuild text as editable PPT text only as a separate follow-up workflow.
- For semi-editable output, still generate the full page with text first; then optionally rebuild title/body/data after the image package is complete.
- For frequently updated charts or process diagrams, still render the confirmed chart/table text into the image if real data is available, and recommend later editable reconstruction.

Delivery-shape options:

| Shape | Use When | Risk |
|---|---|---|
| Quick visual draft | internal direction, mood, one-off preview | almost not editable |
| Image-version PPT | one-time talk or short-term proposal | text/data changes require regeneration |
| Semi-editable draft | most business projects where text changes are likely | visual background remains hard to edit |
| Editable/source reconstruction | long-term reuse, pitch, consulting, corporate templates | higher production cost |

Before full batch generation, create or confirm a global style prompt and 1-2 anchor pages when possible: cover plus a dense content/data page. Do not generate many pages before the style anchor is accepted.

## 10. Review And Delivery

Goal: turn an AI draft into a real deliverable.

Classify the draft first:

- quick visual draft
- image-version PPT
- semi-editable draft
- editable delivery draft

Then run five review rounds:

1. Target review: does the deck complete the original communication task?
2. Logic review: can each page connect through a clear "because -> therefore" chain?
3. Fact review: are data, names, cases, policies, screenshots, and AI visuals defensible?
4. Expression review: is each page clear, readable, and speakable?
5. Delivery review: can the recipient open, present, edit, and reuse the files as promised?

Required final support:

- speaker notes or complete manuscript
- likely defense questions and backup-page suggestions
- revision log if feedback was handled
- delivery checklist with editable range and known risks
- final 30-minute send checklist: content, visual, file, presentation, sending

Image-version PPTX packaging is required after full-page images are generated. If editable PPTX packaging is requested, use the delivery-shape decision to decide whether to hand off to semi-editable reconstruction or full editable deck workflow.
