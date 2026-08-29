---
name: academic-figure-prompt
description: Writes detailed English prompts for AI image tools (official Gemini, ChatGPT Images, Midjourney, DALL-E) to produce conference-style academic diagrams — frameworks, network architectures, pipelines, module details, comparison/ablation layouts, and data-pattern grids. Use when the user asks for a paper figure prompt, academic diagram prompt, architecture-diagram prompt, NeurIPS/ICLR/CVPR-style figure, or provides a paper and wants image-generation prompts. Does not call image APIs and does not generate pixels.
---

# Academic Figure Prompt

English-first skill that writes **image-generation prompts**, not the figures themselves. Output is a long English prompt the user pastes into an image tool they already trust.

For numerically accurate plots from real data, use `scientific-toolkit-skill` (matplotlib/MATLAB). For manuscript prose, use `research-writing-skill`. For Word/PPT, use `office-academic-skill`.

Derived from [LigphiDonk/academic-figure-generator](https://github.com/LigphiDonk/academic-figure-generator) (MIT). Bash tool grant removed. Image-API defaults from that repo are **not** used.

## Safety (non-negotiable)

This skill is prompt text only.

- **Do not** call image APIs, HTTP endpoints, or the LigphiDonk FastAPI/React app.
- **Do not** use `api.keepgo.icu`, `tpkcur.xyz`, NanoBanana reseller URLs, or any undocumented relay.
- **Do not** request shell, bash, network, or package-install tools. Read only files the user attached or named.
- **Do not** invent architecture blocks, dimensions, formulas, or module names that are not in the source paper.
- The deliverable is a markdown prompt block. The user copies it into **official Gemini**, **ChatGPT Images**, **Midjourney**, or another tool they already use. If they have not named a tool, ask — do not pick a third-party relay.
- Unpublished, clinical, or company manuscripts still leave the machine when this chat sends them to the model provider. If the file looks confidential and the user has not confirmed, ask before reading it.

## Styles

Ask which style to use if the user has not said:

| Style | When | Reference |
|-------|------|-----------|
| **Classic** (default) | Nature/IEEE/CVPR-like: white boxes, thin coloured borders, grey arrows, colour-blind-safe palettes | [references/classic-style.md](references/classic-style.md) |
| **Pastel / modern ML** | ICLR/NeurIPS 2024–25 airy look: white canvas, white panels, rounded font, pastel tokens | [references/pastel-style.md](references/pastel-style.md) |

Load only the matching reference file.

## Workflow

### 1. Understand the paper

Read the source the user provided (LaTeX, Word, PDF, or pasted sections). Extract:

- Core concepts, method, model architecture, data flow
- Where a figure is actually needed
- Symbols, variable meanings, tensor dimensions

Stop if the source does not contain enough structure to draw honestly. Ask for the missing section rather than guessing.

### 2. Reference image (optional)

If the user supplied a reference figure, extract palette hex values, layout direction, box style, annotation style, information density, and special elements (skip connections, dashed groups, legends). The reference overrides presets.

### 3. Palette (required unless already specified)

Show the palette table from the chosen style file and **wait** unless the user already named a scheme or said “use the reference figure.”

Default classic scheme if they say “just pick one”: **A — Okabe–Ito** (colour-blind safe).

Custom palettes: user supplies hex values. Public palette tools they can use themselves: [Coolors](https://coolors.co), [ColorBrewer](https://colorbrewer2.org), [Viz Palette](https://projects.susielu.com/viz-palette). Do not fetch those sites on their behalf.

### 4. Write the prompt

Follow the four-layer (classic) or three-layer (pastel) template in the reference file. Every module box must contain sub-content — no empty placeholders. Prefer long and complete over short and pretty.

### 5. Self-check

Use the checklist in the reference file before delivering.

## Output format

Surround the image prompt in a fenced code block. Keep commentary in English.

```markdown
### Figure X.Y — [English title]

Type: [framework / architecture / module detail / comparison / data grid]
Palette: [scheme name]
Suggested aspect: [e.g. 16:9 or 3:2]
Image tool: [only if the user named one; otherwise “paste into your usual official image tool”]

​```
[full English image prompt]
​```
```

If generating several figures for one paper, group by section and mark a suggested drawing order (overview first, then module zooms).

## Grounding rules

- Prompt language is always English (image models follow English more reliably). Explanations stay English unless the user asks otherwise.
- Domain-adapt thumbnails (spectra, trajectories, anatomies) to the paper’s field.
- Do not use "..." or "etc." to skip components that appear in the paper.
- AI-generated diagrams are **illustrative**. They are not publication-ready data figures. Say so if the user might submit them as measured results.
