# Classic academic figure style

White-dominant, thin coloured borders, grey arrows. Suited to Nature / Science / IEEE / CVPR-like diagrams.

## Palettes

Present this table in Step 3 of the skill and wait for a choice.

| # | Name | Positioning | Primary | Secondary | Accent |
|---|------|-------------|---------|-----------|--------|
| A | Okabe–Ito (default) | Colour-blind safe; Nature / CVPR | Steel Blue `#0072B2` | Warm Orange `#E69F00` | Bluish Green `#009E73` |
| B | Blue monochrome | Restrained module-detail figures | Navy `#0072B2` | Medium Blue `#4A90D9` | Light Blue `#A0C4E8` |
| C | Teal + Amber | Modern ICLR / NeurIPS | Deep Teal `#00897B` | Amber `#FFB300` | Soft Grey `#ECEFF1` |
| D | Navy + Coral | IEEE journal | Deep Navy `#1A3A5C` | Coral `#E05A47` | Warm Sand `#F5ECD7` |
| E | Slate + Violet | Medicine / bioinformatics | Slate Blue `#3F51B5` | Muted Violet `#7E57C2` | Pale Lavender `#EDE7F6` |
| F | Forest + Gold | Natural-science journals | Forest Green `#2E7D32` | Gold `#C49A00` | Cream `#F9F6EE` |
| G | Minimal Grey | arXiv technical report; one user accent | Charcoal `#263238` | Steel `#546E7A` | User-specified accent |
| H | Custom | User hex values or a reference figure | — | — | — |

### A — Okabe–Ito (default)

| Role | Colour | Use |
|------|--------|-----|
| Primary | Steel Blue `#0072B2` | Core borders, section labels, main arrows |
| Secondary | Warm Orange `#E69F00` | Secondary borders |
| Accent | Bluish Green `#009E73` | Output modules (sparingly) |
| Warning | Vermillion `#D55E00` | Rare highlights |
| Fill | White `#FFFFFF` | All content boxes |
| Section background | Faint Grey `#F7F7F7` | Large groupings |
| Neutral border | Light Grey `#CCCCCC` | Ordinary 1 px boxes |
| Text | Charcoal `#333333` | Labels |
| Arrows | Dark Grey `#4D4D4D` | Connectors |
| Notes | Medium Grey `#666666` | Captions |

### B — Blue monochrome

Navy `#0072B2` labels; Medium Blue `#4A90D9` main borders; Light Blue `#A0C4E8` secondary; Pale Blue `#EBF3FA` groupings; White fills; Grey `#999999` arrows; Charcoal text.

### C — Teal + Amber

Deep Teal `#00897B`; Amber `#FFB300`; Soft Grey-Blue `#ECEFF1` groupings; White fills; Light Grey `#CFD8DC` borders; Dark Slate `#263238` text; Medium Grey `#607D8B` arrows.

### D — Navy + Coral

Deep Navy `#1A3A5C`; Coral `#E05A47`; Warm Sand `#D4A96A` outputs; Ivory `#F9F6EE` groupings; White fills; Light Warm Grey `#D4C5B0` borders.

### E — Slate + Violet

Indigo `#3F51B5`; Muted Violet `#7E57C2`; Teal `#26A69A` outputs; Pale Lavender `#EDE7F6` groupings; White fills; Light Purple Grey `#C5CAE9` borders; Deep Indigo `#1A237E` text.

### F — Forest + Gold

Forest Green `#2E7D32`; Antique Gold `#C49A00`; Warm Cream `#F9F6EE` groupings; White fills; Sage `#A5D6A7` borders; Dark Forest `#1B5E20` text; Warm Grey `#795548` arrows.

### G — Minimal grey + one accent

One accent (default Steel Blue `#0072B2`) on 1–2 core boxes only. Charcoal `#263238` labels; Slate `#546E7A` main borders; Medium Grey `#90A4AE` secondary; Light Grey `#ECEFF1` groupings; Grey `#B0BEC5` ordinary borders.

### H — Custom

```
Primary: #XXXXXX (core borders / section labels)
Secondary: #XXXXXX (secondary / emphasis)
Accent: #XXXXXX (outputs, optional)
Background: #XXXXXX (very light grouping)
Text: #XXXXXX (dark)
```

## Colour don'ts (anti “AI-slop” look)

| Avoid | Use instead |
|-------|-------------|
| 4–5 coloured background panels | White + very faint grey grouping |
| Saturated header banner bars | Small-caps labels + grey rules |
| Different fill colour per module | White fill, colour only on borders |
| Full-colour thumbnails | Mono or two-colour thumbnails |
| Five or more hues at once | At most three hues + greys |
| Rainbow / gradients | Flat solid colours |

## Four-layer prompt template

Every prompt needs all four layers.

### Layer 1 — Global description

```
A highly detailed, information-dense academic paper [type] diagram in the style of
top-tier [venue] publications. The diagram illustrates [topic], arranged as
[layout, e.g. "a rich multi-stage left-to-right pipeline with parallel pathways,
embedded thumbnail visualizations, and dense annotations"].
```

Type vocabulary: architecture, framework, pipeline, flowchart, comparison, ablation, network architecture, module detail, data flow, system overview.

### Layer 2 — Section-by-section

Separate regions with `=== SECTION NAME ===`. Each region must include:

| Element | Requirement | Example phrasing |
|---------|-------------|------------------|
| Background panel | Very light fill + hex | `very faint grey #F7F7F7 background panel` |
| Section label | Small-caps + thin grey rule | `small-caps Steel Blue label "ENCODER"` |
| Module box | White fill + coloured/grey border | `white rounded-rectangle box with Steel Blue border` |
| Substructure | Interior components | `containing three parallel branches...` |
| Embedded thumbnail | Small mono viz | `a small monochrome FFT spectrum bar chart thumbnail` |
| Formula | LaTeX-style | `with formula "HT = 1/(1 + d/d₀)"` |
| Dimensions | Tensors / vectors | `labeled "X ∈ R^(120×6)"` |
| Arrows | Type + label | `thin arrow labeled "30-step predicted trajectory"` |

No empty boxes.

### Layer 3 — Global annotations

- Dimensions on major arrows: `"R^(120×6)"`, `"R^14"`
- Feedback: `dashed feedback arrow from output back to input`
- Legend if needed
- Skip connections: `skip connection dashed arrow from Stage 1 to Stage 3`

### Layer 4 — Style specifications

Append a full STYLE SPECIFICATIONS block using the chosen palette hex values, plus the don'ts list.

## Figure-type templates

### Overall framework

```
Structure: [input] → [stage 1] → [stage 2] → ... → [output]
- Stages: small-caps labels + thin grey rules (no coloured banners)
- Core modules: primary border; secondary: secondary border; ordinary: Grey
- White fills only
- Arrows between stages carry dimension + meaning
- 2–4 submodules per stage, each with a mono thumbnail
- Feedback / skip as grey dashed lines
```

### Network architecture

```
Structure: [input] → [encoder stack] → [core module with parallel branches] → [heads]
- Parallel branches distinguished by border colour, white fills
- Each branch: operation name + mono thumbnail
- Residuals: grey dashed curved arrows
- Dimensions in small grey type at each transform
- Repeated layers: grey dashed "×N" box
```

### Module detail

```
Structure: [input] → [op 1] → [intermediate] → [op 2] → [output]
- Each step in its own white box; key ops primary border; others Grey
- Intermediates as mono thumbnails (spectrum, heatmap)
- Skip/residual: grey dashed
- Formula beside the matching box
```

### Comparison / ablation

```
N columns, one variant each
- Shared backbone: identical grey borders
- Differences: primary/secondary border + grey dashed callout
- Column titles in small-caps
- Optional metric bars at bottom using only primary + secondary + Grey
```

### Data / behaviour grid

```
1×N cells
- White cell, thin grey border, primary small-type header
- Typical mono/two-colour viz per class
- Primary vs secondary for positive/negative classes if that contrast exists
- Shared axis at the bottom if relevant
```

## Thumbnail vocabulary

| Data | Phrasing |
|------|----------|
| Time series | `a small time-series waveform thumbnail` |
| Spectrum | `a small frequency spectrum bar chart thumbnail` |
| Attention | `a small monochrome attention heatmap grid thumbnail` |
| Trajectory | `a small 3D orbital trajectory curve thumbnail` |
| Distribution | `a small probability distribution bar chart thumbnail` |
| Decision tree | `a small decision tree branching diagram thumbnail` |
| Confusion matrix | `a small confusion matrix heatmap thumbnail` |
| Network layer | `a small neural network layer diagram thumbnail` |
| Feature vector | `a small horizontal feature vector bar visualization` |
| Scatter | `a small scatter plot with cluster coloring thumbnail` |
| Receptive field | `a progressively larger receptive field grid icon` |
| Convolution kernel | `a small convolution filter kernel grid thumbnail` |
| Gradient flow | `a small gradient flow direction arrow diagram` |
| Loss curve | `a small training loss convergence curve thumbnail` |
| ROC | `a small ROC curve with AUC shading thumbnail` |
| Example image | `a small example image/photo thumbnail` |
| Point cloud | `a small 3D point cloud visualization thumbnail` |
| Spatial heatmap | `a small spatial heatmap overlay thumbnail` |

Adapt to perfusion, devices, or clinical diagrams when that is the paper’s field (circuit, cannula, oxygenator, NIRS montage, and so on) — still as illustrative thumbnails, not measured plots.

## Quality checklist

- [ ] Every box has interior content (sub-box, thumbnail, or formula)
- [ ] At most 2–3 hues
- [ ] ≥70% white / near-white; no coloured banners
- [ ] Colour on borders, not fills
- [ ] Partitions via small-caps + grey rules
- [ ] Major data-flow arrows have dimensions
- [ ] Key operations have formulas from the paper
- [ ] At least half of modules embed a thumbnail
- [ ] No paper component omitted
- [ ] Parallel paths, residuals, and feedback are explicit
- [ ] STYLE SPECIFICATIONS block present, with hex values and don'ts
- [ ] No "..." / "etc."
- [ ] Still readable if printed greyscale
