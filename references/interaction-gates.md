# Interaction Gates

This skill is human-in-the-loop. Do not generate the full planning brief, images, or delivery files before the relevant gates are answered.

## Hard Stop Rule

At every gate:

1. Ask only the questions needed for the next stage.
2. End the response after the question.
3. Wait for the user to answer.
4. If the answer is incomplete, ask one concise follow-up round.
5. Continue only after the user confirms or explicitly says to skip.

Do not silently assume audience, target action, page count, missing evidence, mainline, page order, style, delivery shape, or text editability.

When content depends on external facts, proactively search the web and cite sources. Do not use source-unclear information.

## Gate A: Intake Questions

Ask before task diagnosis:

```text
为了先判断任务，我需要确认 10 件事：

1. 这份 PPT 给谁看？请尽量具体到角色、职级、决策权。
2. 你希望对方看完后做什么？例如批准、购买、预约沟通、学会操作、认可方案。
3. 使用场景是什么？现场讲、线上讲、发 PDF 自看、答辩、路演、内部评审？
4. 这份 PPT 主要是给人自己阅读，还是配合现场/线上演讲？阅读型文字可以稍多、句子更完整；演讲型文字要更少、更大。
5. 主题和已有资料是什么？可以直接粘贴资料，也可以先列清单。
6. 预计多少页？如果不确定，我可以根据目标建议页数。
7. 哪些内容必须出现？
8. 哪些内容不能出现或需要规避？
9. 交付时间、语气和正式程度有什么要求？
10. 这版后续是否要反复修改或复用？你希望交图片版、半可编辑版，还是可编辑源文件？
```

Stop after asking.

## Gate B: Task Brief Confirmation

After analyzing intake, present:

- PPT type
- target audience
- current belief
- desired judgment
- core resistance
- target action
- success standard
- forbidden writing

Ask:

```text
上面这份任务判断有没有偏差？尤其是“目标动作”“核心阻力”和“成功标准”是否准确？请确认或修改后，我再整理资料包。
```

Stop after asking.

## Gate C: Materials Confirmation

After organizing materials, present:

- strongest evidence
- verified web sources with title, organization, URL, date if available, and supported claim
- weak evidence
- missing evidence
- risky claims
- unusable or forbidden expressions

Ask:

```text
这些缺口里，哪些可以补充？哪些暂时补不了、需要在策划案里标成风险？我会把已联网查到且来源清楚的信息写入 `资料来源表.md`；来源不清楚或无法核验的信息不会当成证据使用。确认后我再生成主线方案。
```

Stop after asking.

## Gate D: Mainline Selection

Present 2-3 candidate mainlines with structure, strength, and risk.

Ask:

```text
你倾向选哪条主线？也可以指定“用 A 的角度 + B 的结构”。确认后我再拆页面结构。
```

Stop after asking.

## Gate E: Page Plan Confirmation

Present a compact table:

```text
页码 / 页面任务 / 结论型标题 / 证据 / 视觉方向
```

Ask:

```text
这个页序是否符合你的讲述节奏？是否需要加页、删页、合并或调整顺序？确认后我再写逐页脚本、页面文案、数据页和素材规划。
```

Stop after asking.

## Gate F: Style Recommendation Confirmation

Read bundled `references/PPT制作风格库.md`. Present 3-5 styles using the exact field names from that file.

Ask:

```text
我建议主风格选【编号：风格名称】，备选为【编号：风格名称】。你确认这个方向吗？你也可以直接指定风格编号，例如 `PPT-S86`；如果想更正式、更科技、更克制或更有冲击力，请告诉我，我会重新筛选。
```

Stop after asking.

## Gate G: Delivery Shape Confirmation

After style selection, recommend a delivery shape:

- quick visual draft
- image-version PPT
- semi-editable draft
- editable/source reconstruction

Ask:

```text
按目前需求，我建议交付形态为【形态】，原因是【一句话理由】。注意：PushiPPT 生图阶段会把确认后的标题、核心结论和必要标签直接生成在图片里，但图片中不加页码、logo、页脚或水印；如果后续需要可编辑文字，那是生图完成后的半可编辑或全可编辑重构流程。你确认这个交付方向吗？
```

Stop after asking.

## Gate H: Final Brief Save

After producing the full brief, ask:

```text
这份策划案是否需要保存成 Markdown 文件？如果需要，我会保存为 `PPT制作策划案.md`，再进入页面生产表确认。
```

Stop after asking unless the user already asked to save the file.

## Gate I: Page Production Table Confirmation

Before image generation, present:

```text
页码 / 页面类型 / 页面目的 / 用途模式 / 文字密度 / 标题 / 进图内容 / 必须保留信息 / 主视觉 / 产品一致性 / 设计自由度 / 文字策略 / 交付形态 / 风险
```

Ask:

```text
这张页面生产表是否可以作为出图依据？请重点确认每页要直接生成进图片里的标题、核心结论、标签和数据文字；哪些文字必须逐字保留，哪些可以让 imagegen 为了设计效果自行整理；是否涉及需要保持一致的产品图片、产品界面或产品包装；哪些数据页缺少真实数据、不能让 AI 凭空生成。
```

Stop after asking.

## Gate J: Production Confirmation

After saving the brief and page table, show:

- saved brief path
- page production table path
- page count
- selected style
- delivery shape
- expected image count
- text/data strategy: required page content will be rendered directly into images, while imagegen may improve layout, grouping, and supporting visuals
- image exclusion rule: no page numbers, no logos, no watermarks, no footers
- product consistency rule if product visuals are used
- image-version PPTX output path
- manuscript and review output paths

Ask:

```text
策划案和页面生产表已保存。请确认是否按以上页数、风格和交付形态进入 imagegen 生图流程？确认后我会直接调用 imagegen 逐页生成图片，标题、核心结论和必要标签会一起进图，但不加页码、logo、页脚或水印；如涉及产品图，会保持产品外观和界面风格一致；内页标题尽量保持大小和位置一致，封面大标题做特殊美化。全部图片完成后，我会按顺序插入 PPT 生成图片版 PPTX，再生成并保存完整讲稿、审稿清单和交付清单。
```

Stop after asking.

## Gate K: Final Package Review

After image generation, manuscript, review, and delivery checklist are generated, present:

- `PPT制作策划案.md`
- `资料来源表.md`
- `页面生产表.md`
- page image list in order
- `图片版PPTX.pptx`
- `完整讲稿.md`
- `审稿清单.md`
- `答辩问题与备用页建议.md`
- `交付清单.md`
- known risks or pages needing manual correction

Ask:

```text
这些交付物已经生成。是否需要我继续修订某一页图片、调整讲稿语气、补充答辩页，或进入后续可编辑重构流程？
```

Stop after asking.
