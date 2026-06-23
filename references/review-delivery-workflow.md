# Review And Delivery Workflow

Use this after a draft, page images, or production package exists. The goal is to turn an AI draft into a usable deliverable.

## 1. Classify The Draft

First state the current stage:

| Draft Type | Typical Form | Review Focus |
|---|---|---|
| Quick visual draft | page images for direction | style, tone, main visual |
| Image-version PPT | full-page images for presentation | order, text accuracy, one-time usability |
| Semi-editable draft | image backgrounds plus editable text/charts | editability, stable layout, text-image fit |
| Editable delivery draft | text, charts, structure, assets maintainable | accuracy, template rules, reuse cost |

If the user expects editable source files but the current output is image-only, say so and recommend semi-editable or source reconstruction.

## 2. Five-Round Review

Run the rounds in order. Do not start with design polish.

### Round 1: Target Review

Questions:

1. Who is the target audience?
2. What judgment should they form after viewing?
3. Does the deck answer their core concern?
4. Is too much space spent on what we want to say instead of what they need to hear?
5. Is the final action, decision, or next step clear?
6. If only 3 pages remain, which 3 complete the task best?

Output:

```text
page / target contribution / issue / revision suggestion
```

### Round 2: Logic Review

Use the "because -> therefore" test between pages.

Output:

```text
page / page judgment / why previous page leads here / why next page needs it / gap / revision
```

If a page cannot be connected to the previous or next page, remove, move, merge, or rewrite it.

### Round 3: Fact Review

Check at least:

- customer/project/person names
- data source, caliber, time range, and unit
- web source title, publisher, URL, publish/update date, and supported claim
- chart numbers vs body text
- case permission and screenshot authorization
- industry terms
- policies, regulations, and standards
- product capability overclaims
- AI images implying false scenes, devices, customers, or results
- sensitive information and anonymization

Output:

```text
claim / current evidence / risk / required verification / safer wording
```

Rule: AI may identify risks but must not invent sources, use source-unclear information, or confirm unknown facts.

### Round 4: Expression Review

For every page, write:

```text
看完这一页，听众应该带走的判断是：____
```

Check:

- title is a judgment, not a label
- body copy matches the confirmed self-reading or speaking mode
- no page uses a large paragraph
- explanations belong in speaker notes, not on the page
- data page passes the "hide the title" and "hide the chart" tests
- visual style, hierarchy, color, spacing, icons, and projection readability are stable
- inner-page title size and position are consistent
- cover title has special beautified treatment and stronger hierarchy than inner pages
- no generated image contains page numbers, logos, watermarks, or footers
- product visuals remain consistent across pages when products appear

Output:

```text
page / current issue / revised title / keep on page / move to notes or appendix
```

### Round 5: Delivery Review

Check whether the recipient can really use the files:

- editable range matches promise
- fonts are available or PDF/image backup exists
- images are clear and not stretched
- image-version PPTX exists and uses one generated page image per slide in the correct order
- generated images do not contain page numbers, logos, watermarks, or footers
- product visuals remain consistent if used
- videos, links, and animations work if present
- data/source files are retained
- version naming is clear
- file size can be sent
- final presentation plays full-screen

Output:

```text
item / status / risk / action
```

## 3. Feedback Handling

If feedback exists, organize it before editing:

```text
id / source / page / original feedback / type / action / status
```

Types:

- task
- logic
- fact
- expression
- visual
- delivery

If feedback conflicts, surface the conflict and ask the user to decide.

## 4. Speaker And Defense Support

After page images are generated, create `完整讲稿.md` as a complete spoken manuscript. Do not replace it with brief notes unless the user explicitly asks for a notes-only version.

For each page:

```text
这一页要讲什么：
讲述顺序：
注意：
过渡：
```

Also create `答辩问题与备用页建议.md`:

- target/value questions
- data/evidence questions
- feasibility questions
- cost/resource questions
- risk/alternative questions
- backup page or material needed for each question

## 5. Delivery Package Shapes

### Image-Version Package

```text
交付包/
  PPT/
    项目名_图片版_v03.pptx
    项目名_图片版_v03.pdf
  images/
  prompts/
  notes/交付说明.md
```

Delivery note must state: pages are mostly full images and not suitable for broad editing.

For PushiPPT imagegen production, this image-version PPTX is required after page images are generated unless local PPTX tooling is unavailable. In that case, record the blocker and keep the ordered image list ready for packaging.

### Semi-Editable Package

```text
交付包/
  PPT/
    项目名_半可编辑交付版_v03.pptx
    项目名_半可编辑交付版_v03.pdf
  assets/
  data/
  docs/
    交付说明.md
    修改记录.md
```

Delivery note must state which text/charts are editable and which AI visuals are image assets.

### Editable Source Package

```text
交付包/
  01_PPT/
  02_assets/
  03_data/
  04_docs/
    交付说明.md
    设计规范.md
    页面修改指南.md
    修改记录.md
  05_backup/
```

Use only when the project requires maintainable source files and a reconstruction workflow has been executed.

## 6. Final 30-Minute Checklist

Content:

```text
客户名称、项目名称、日期、目录、数据、口径、来源链接、错别字、敏感信息、附录顺序
```

Visual:

```text
封面标题特殊设计、内页标题位置一致、字体层级、无页码/无logo/无页脚/无水印、产品一致性、图片拉伸、背景压字、图表颜色、深色页投影
```

File:

```text
PPTX 打开、PDF 打开、文件名、版本号、文件大小、视频/外链、字体、备用版本
```

Presentation:

```text
全屏播放、动画顺序、跳转链接、讲稿备注、备用页位置、预计时间
```

Sending:

```text
收件人、附件、正文说明、压缩包/网盘、可编辑范围提醒、PDF 预览
```

If time only allows one check, play from the first slide to the last slide full-screen.
