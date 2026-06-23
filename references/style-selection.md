# Curated Style Selection

Use this file for the final style recommendation section of the planning brief.

## Source

Default source, bundled inside this skill. It currently contains 180 styles: 40 curated mother styles plus 140 reverse-engineered extension styles.

```text
references/PPT制作风格库.md
```

Do not use external style folders by default. Use the bundled style file first so this skill is self-contained. Only use an external style library if the user explicitly supplies or requests one.

## Required Output Format

When recommending a style, preserve the curated library's field names.

For each shortlisted style:

```text
- PPT风格名称：
- 编号：
- 类型：
- 适用场景：
- 适用主题：
- 主色调：
- 辅助色：
- 强调色：
- 材质：
- 纹理：
- 光影：
- 风格特点：
- 风格元素：
- 风格提示词：
- 合并参考：
- 匹配理由：
- 风险：
```

For the final chosen style, add:

```text
- 针对本项目的适配说明：
- 哪些页面最适合体现该风格：
- 需要弱化的元素：
- 需要强化的元素：
- 制作注意事项：
```

## Selection Logic

Use these matching signals:

1. PPT type: report, decision, sales, training, pitch, communication, data.
2. Audience: senior executives, clients, investors, students, public audience, internal team.
3. Scene: live presentation, PDF self-reading, defense, roadshow, internal review.
4. Information density: low, medium, high.
5. Proof needs: data-heavy, screenshot-heavy, case-heavy, story-heavy.
6. Tone: credible, persuasive, training-friendly, premium, academic, energetic.
7. Industry: AI, manufacturing, medical, government, finance, education, consumer brand, culture.
8. Visual keyword match: for PPT-S41 through PPT-S180, search the bundled style library by keywords such as `涂鸦`, `像素`, `水墨`, `玻璃拟态`, `软3D`, `医疗`, `旅行`, `电竞`, `展陈`, `微缩`, `仪表盘`, `复古`, or other user-provided visual cues.

## Common Mappings

- Management report: PPT-S01, PPT-S02, PPT-S04, PPT-S05
- Consulting delivery: PPT-S02, PPT-S01, PPT-S06
- Data report: PPT-S04, PPT-S07, PPT-S17
- AI strategy/product: PPT-S09, PPT-S10, PPT-S11, PPT-S14
- Manufacturing/engineering: PPT-S13
- Product launch: PPT-S18, PPT-S15, PPT-S10, PPT-S19
- Pitch deck: PPT-S24, PPT-S10, PPT-S18
- Training/course: PPT-S28, PPT-S40, PPT-S29
- Government/party: PPT-S26
- Medical/clinical: PPT-S25
- ESG/public welfare: PPT-S27
- Regional/planning: PPT-S30
- Story/keynote: PPT-S31, PPT-S33, PPT-S34

For more specific visual directions, also search and shortlist from PPT-S41 to PPT-S180. These extension styles are more granular than the first 40 mother styles and are useful when the user asks for a precise mood, material, scene, or reference-like visual language.

## User-Specified Style ID

If the user directly specifies a style编号 such as `PPT-S86`, load that style from `references/PPT制作风格库.md` and use it as the primary style unless the ID is missing or clearly conflicts with an explicit brand/scene constraint.

When a user-specified style is used:

- still summarize the style using the library's exact fields
- state why it fits or where it may be risky
- adjust page density, typography, and visual emphasis to the confirmed self-reading or speaking mode
- do not replace the user's chosen style with an automatic recommendation unless you first explain the mismatch and ask for confirmation

## Confirmation Rule

Style choice is a gate. Present candidates, recommend one, and tell the user they may also choose by exact style编号. Stop and wait for user confirmation before writing the final brief.
