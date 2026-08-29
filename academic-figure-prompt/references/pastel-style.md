# Pastel / modern ML figure style

Airy ICLR / NeurIPS / ICML 2024–25 look: pure white canvas, white floating panels, rounded geometric sans, pastel tokens. Use only when the user asks for this style.

## Hard style rules

### 1. White canvas + white panels + faint shadow

```
Canvas = pure white #FFFFFF. No gradient, no grey wash, no warm tint.
Panels = white #FFFFFF rounded rectangles + very faint soft drop-shadow
         (3px blur, 1px y-offset, rgba(0,0,0,0.06)).
Separation = shadow only, not grey fill and not a heavy border.
```

Do not fill panels with `#F5F5F5`. Do not use a gradient canvas.

### 2. Rounded friendly type

```
Font = rounded geometric sans (Nunito / Poppins / Quicksand / Comfortaa)
Titles = semi-bold–bold (600–700), ~16–18 pt
Body = regular (400), ~10–11 pt
Math = italic serif (Computer Modern / STIX)
```

Not sharp Helvetica/Arial. The rounded face is the style.

### 3. Packed, not sparse, not cramped

Each panel is full of tokens, curves, formulas, icons, arrows, with 8–12 px micro-gaps. “Thoughtfully packed,” not empty and not a wall of type.

### 4. Floating elements, no nested boxes

Elements sit on the white panel. No box-in-box. Concept names use pale pill badges.

### 5. Colour lives in tokens, type, and curves

Panel and canvas stay white. Colour is pastel token squares (fill + 1 px darker border), semantic keyword colour, curve stroke, and tiny category dots.

## Five colour carriers

| Carrier | How | Example phrasing |
|---------|-----|------------------|
| Token square | 10–14 px rounded square, pastel fill + darker 1 px border | `soft blue #BBDEFB square with 1px #90CAF9 border, "s₁" label` |
| Coloured type | Keyword in a semantic hue | `bold coral #E05555 text "Exciter"` |
| Pill | Very pale fill, matching thin border | `faint green-tinted pill badge "Random Forest"` |
| Curve | Thumbnail stroke colour | `sigmoid curve in warm amber #DAA520 line` |
| Dots | Tiny category markers | `5 tiny circles in blue, pink, amber, purple, green` |

## Palettes

Wait for a choice unless the user already specified.

| # | Name | Token fills | Type emphasis |
|---|------|-------------|---------------|
| P1 | Warm ML | Pink `#FFD0D0` · Blue `#BBDEFB` · Yellow `#FFF3C4` · Purple `#E1BEE7` · Green `#C8E6C9` | coral `#E05555` · teal `#1A9988` · purple `#6A5ACD` · green `#3A8F3A` |
| P2 | Cool Research | Blue `#B3E5FC` · Indigo `#C5CAE9` · Blue-grey `#CFD8DC` · Cyan `#B2DFDB` · Lavender `#D1C4E9` | navy `#1565C0` · indigo `#3949AB` · teal `#00897B` |
| P3 | Earthy Warm | Sand `#FFE0B2` · Camel `#D7CCC8` · Sage `#C8E6C9` · Grey `#E0E0E0` · Taupe `#EFEBE9` | brown `#6D4C41` · olive `#827717` · forest `#2E7D32` |
| P4 | Custom | User hex | User hex |

## Layout

Panel count and size follow content. Do not force a symmetric 2×2.

- 2–5 panels; main flow can be larger
- ~20 px between panels
- Common arrangements: uneven 2×2, 1+2, 3-panel asymmetric, horizontal pipeline

## Prompt structure

### Layer 1 — Global

```
A richly detailed academic paper [type] diagram in the modern style of top-tier
ICLR/NeurIPS 2024-2025 publications. The diagram illustrates [topic].

CANVAS: Pure flat white (#FFFFFF). No gradient, no tint, no grey.

PANELS: [N] large rounded-rectangle panels (radius ~20px) with white (#FFFFFF)
fill and very subtle soft drop-shadow (3px blur, 1px y-offset, rgba(0,0,0,0.06)).
Panels sit on the white canvas, distinguished only by their barely-perceptible
shadow.

FONT: Friendly rounded geometric sans-serif (Nunito / Poppins / Quicksand).
Titles semi-bold to bold (600-700), ~16-18pt. Body regular (400), ~10-11pt.
Math in italic serif (Computer Modern).

CONTENT DENSITY: Panels are FILLED with content — tokens, curves, formulas, icons,
arrows — with consistent 8-12px micro-spacing. "Thoughtfully packed" not "sparse".

NO NESTED BOXES: Elements float directly on white panel surfaces. Only pill-shaped
labels for concept names.

Arranged as [layout].
```

### Layer 2 — Panels

Separate with `=== PANEL: [name] ===`.

```
=== PANEL: [name] ===

White panel, subtle shadow, rounded corners ~20px.

Title: Bold [colour] rounded font "[title]" (~18pt).

Content (packed, floating elements):
  [element list]
```

| Element | Phrasing | Note |
|---------|----------|------|
| Token sequence | `3 soft blue #BBDEFB squares with 1px #90CAF9 border, labeled "x  y  z"` | Always state the border |
| Pill | `a faint green pill badge "Random Forest" in green text` | Pale fill |
| Coloured title | `bold coral #E05555 text "Exciter"` | Floats on the panel |
| Curve thumbnail | `a small sigmoid in warm amber #DAA520 line (~30×20px), tiny grey axes` | Drawn on the panel |
| Formula | `italic serif formula: "X_k → f_θ(X_k)"` | From the paper |
| Icon | `a small satellite schematic in thin grey lines with blue dot trail` | Specific, not generic |
| Tree | `a binary tree in thin grey lines, leaf nodes as tiny colored circles` | Multiple levels |
| Arrow | `thin 1.5px dark grey #555 arrow with small arrowhead` | Simple |

### Layer 3 — Style specifications

```
=== STYLE SPECIFICATIONS ===

Canvas: Pure white #FFFFFF. No gradient.
Panels: White #FFFFFF, radius ~20px, soft shadow (3px blur, rgba(0,0,0,0.06)).
Font: Rounded sans-serif (Nunito/Poppins/Quicksand). Titles bold ~16-18pt,
body regular ~10pt, math italic serif. Warm and friendly, NOT angular Helvetica.
Density: Panels FILLED with content. 8-12px micro-spacing. No dead space.
Structure: Floating elements on white panels. No nested boxes.

Token colors (with 1px darker border):
  - [semantic role]: [fill] / [border] / [text emphasis]

Arrows: 1-1.5px dark grey #555, neat arrowheads. Some curved.
Pill labels: Faint pastel tint + thin matching border, rounded ~8px.
Colored text: Concept names in semantic colors (coral, teal, purple, green).

No 3D, no gradients on elements, no heavy shadows. Flat vector.
Resolution: [width] × [height] px minimum.
```

## Interior vocabulary

### Token squares (Warm ML defaults)

| Role | Phrasing |
|------|----------|
| State / input | `soft blue #BBDEFB square, 1px #90CAF9 border, "s₁" label` |
| Action / prediction | `soft pink #FFD0D0 square, 1px #EF9A9A border, "a₁" label` |
| Feature | `soft purple #E1BEE7 square, 1px #CE93D8 border` |
| Reward / output | `soft green #C8E6C9 square, 1px #A5D6A7 border` |
| Metric | `soft amber #FFF3C4 square, 1px #FFE082 border` |

### Curves

| Type | Phrasing |
|------|----------|
| Loss | `descending curve in coral #E05555 line, tiny grey axes` |
| Sigmoid | `sigmoid curve in warm amber #DAA520 line` |
| Spectrum | `bar spectrum with 6 bars in soft pink, varying heights` |
| Distribution | `5 colored bar segments of varying widths` |
| Oscillation | `oscillating wave in amber line` |

### Icons

| Type | Phrasing |
|------|----------|
| Cycle | `4-node cycle: "A"→"B"→"C"→"D" in tiny colored text with curved arrows` |
| Network | `input bars → hidden layers with dot connections → output, thin grey lines` |
| Tree | `binary branching tree, grey lines, colored circle leaf nodes` |
| Fan of trajectories | `multiple curves fanning out from a point, solid mean + dashed bounds` |
| Pyramid | `3 levels of increasing width, converging to ⊕ fusion` |
| Funnel | `wide dot cluster → converging lines → narrow column of tokens` |

## Quality checklist

- [ ] Canvas `#FFFFFF`, no grey wash
- [ ] Panel fill `#FFFFFF`, lift from soft shadow only
- [ ] Nunito / Poppins / Quicksand named; not Helvetica
- [ ] Panels packed (tokens + curves + formulas + icons)
- [ ] 8–12 px gaps; no overlap
- [ ] No nested boxes
- [ ] Pills for concept names
- [ ] Semantic coloured keywords
- [ ] Tokens have 1 px darker borders
- [ ] At least some real illustrations, not only squares
- [ ] Math in italic serif, from the paper
- [ ] Reads as a 2024 ICLR-style figure, not a 2016 PowerPoint
