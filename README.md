# PushiPPT Brief

`pushippt-brief` is a Codex skill for creating source-backed PPT production briefs and image-version PPT handoff packages.

它适合用在 AI PPT、商业汇报、路演、课程型演示、答辩材料等场景：先把需求、受众、证据、主线、页面脚本、视觉方向、数据页、素材计划和交付形态整理成完整策划案，再进入整页生图和图片版 PPTX 生产。

## What It Does

This skill helps Codex produce:

- PPT production planning brief
- audience and task diagnosis
- source-backed research table
- persuasive narrative options
- slide-by-slide script
- page copy and text-density strategy
- visual system recommendation
- data-page and asset planning
- page production table
- image-generation prompts for full-slide page images
- image-version PPTX handoff plan
- speaker manuscript, review checklist, Q&A prep, and delivery checklist

## Core Workflow

The skill follows a gated workflow:

1. Intake and task diagnosis
2. Material and source review
3. Mainline selection
4. Page plan and slide script
5. Page copy and text-density decision
6. Visual style recommendation
7. Delivery-shape decision
8. Final planning brief
9. Page production table
10. Image-generation package and PPTX handoff
11. Five-round review and final delivery checklist

The workflow intentionally separates planning from production. It should not generate slide images before the planning brief and page production table are confirmed.

## Repository Structure

```text
.
├── README.md
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── course-1-10-workflow.md
    ├── interaction-gates.md
    ├── logic-models.md
    ├── planning-brief-schema.md
    ├── PPT制作风格库.md
    ├── production-workflow.md
    ├── review-delivery-workflow.md
    └── style-selection.md
```

## Installation

Clone or download this repository, then place the folder under your Codex skills directory:

```text
C:\Users\<your-name>\.codex\skills\pushippt-brief
```

The final folder should contain `SKILL.md` at its root.

## Usage

In Codex, ask for this skill by name or describe a PPT planning task:

```text
Use pushippt-brief to create a production planning brief for this PPT.
```

or:

```text
帮我用 pushippt-brief 做一个商业汇报 PPT 策划案，包含页面脚本、视觉方向、资料来源表和交付清单。
```

Codex should then follow the gate-based workflow in `SKILL.md` and the files under `references/`.

## Important Rules

- Use public, attributable sources when external facts, market data, product details, or policy claims are needed.
- Separate user-provided materials, verified sources, and unsupported assumptions.
- Do not invent data, citations, customer names, policy validity, or product details.
- Do not generate final page images before the planning brief and page production table are confirmed.
- Generated page images should not include page numbers, watermarks, decorative logos, or footers unless explicitly requested.
- Image-version PPTX is the default production target. Editable PPT reconstruction is a separate later workflow.

## Typical Outputs

The full workflow may generate files such as:

```text
PPT制作策划案.md
资料来源表.md
页面生产表.md
prompts/
PPT页面图片/
PPT/
完整讲稿.md
审稿清单.md
答辩问题与备用页建议.md
交付清单.md
```

## License

No license has been specified yet. Add one before distributing or accepting external contributions.
