# Academic Skills for Claude Code, Codex & Cursor

> Four academic skill packs covering paper writing, Office document generation, research computing, and AI figure-prompt writing.
> Skills load in **Claude Code**, **Codex**, and **Cursor**.

This repository is a private **English-first** localization and security-hardened derivative of
[zLanqing/codex-claude-academic-skills](https://github.com/zLanqing/codex-claude-academic-skills).
See [NOTICE](NOTICE) and [SECURITY.md](SECURITY.md).

---

## Skill overview

| Skill | Core use | Typical scenarios |
|------|----------|-------------------|
| [`research-writing-skill`](#1-research-writing-skill--paper-writing) | Draft, revise, and polish paper sections | Abstract, introduction, methods, experiments, rebuttal |
| [`office-academic-skill`](#2-office-academic-skill--academic-office-documents) | Academic Word/PPT generation and editing | Literature reading reports, group-meeting PPT, defense PPT |
| [`scientific-toolkit-skill`](#3-scientific-toolkit-skill--research-computing) | Research computing and data analysis | MATLAB/Python simulation, statistics, ML, publication figures |
| [`academic-figure-prompt`](#4-academic-figure-prompt--ai-diagram-prompts) | English prompts for AI image tools | Conference-style architecture / pipeline diagrams |

The skills are complementary and can be used together:

```
Paper-writing workflow:
  scientific-toolkit-skill (analysis, data figures)
  → academic-figure-prompt (optional conceptual diagram prompts)
  → research-writing-skill (manuscript prose)
  → office-academic-skill (defense PPT)

Literature-reading workflow:
  office-academic-skill (PDF → Word reading report)
  → office-academic-skill (group-meeting PPT)

Simulation workflow:
  scientific-toolkit-skill (MATLAB/Python + figures)
  → research-writing-skill (methods + results sections)
```

---

## 1. research-writing-skill — Paper writing

**English-first** academic writing for manuscript body text, LaTeX/Overleaf drafts, and theses.

### Features

- Section drafting: abstract, introduction, related work, methods, experiments, discussion, conclusion
- Revision and polishing: logic, terminology consistency, citation accuracy
- Reviewer responses (rebuttal / peer-review response)
- Argument planning: from vague idea to paper outline

### Writing principles

- Default to English; switch language only if the user asks
- Do not invent data, DOI, journal metadata, or experimental results
- Separate source/existing data, user-confirmed content, inference, and suggested extensions
- Prefer measurable claims over vague praise words ("significant", "advanced", "effective")

### Bundled references

| Path | Content |
|------|---------|
| `paper-writing/section_rhetorical_moves/` | Section rhetorical structure guides |
| `paper-writing/writing_checklists/` | Writing self-check lists |
| `paper-writing/figure_templates/` | Figure planning templates |
| `paper-writing/brainstorming_guide.md` | From idea to paper blueprint |

---

## 2. office-academic-skill — Academic Office documents

**English-first** Word and PowerPoint workflows that produce editable `.docx` and `.pptx` files.

### Features

**Word**

- PDF/paper → literature reading report (English by default; Chinese optional on request)
- Structured DOCX generation: headings, tables, figure placeholders, source labels
- Versioned edits of existing Word documents

**PowerPoint**

- Literature report PPT, group meeting PPT, course report PPT
- Opening/midterm/defense PPT (template matching, master cloning)
- Research showcase and science-communication PPT

### PPT quality rules

- One core point per slide; prefer action titles that state the conclusion
- Let figures, formulas, and tables carry the technical argument
- Keep axes, units, legends, formulas, and data sources accurate
- Prefer white or restrained academic backgrounds

### Bundled tools

| Path | Content |
|------|---------|
| `office-docx/` | OOXML-level DOCX check/edit, including XSD schemas |
| `office-pptx/` | OOXML-level PPTX check/edit |
| `thesis-defense-pptx/scripts/` | Thesis context extraction, template clone, slide export, overflow checks (Windows `.ps1` helpers are Windows-only) |
| `report-structure.md` | Default literature report structure and evidence labels |

---

## 3. scientific-toolkit-skill — Research computing

Research computing skill oriented toward **optoelectronic information science and engineering** (examples can be adapted to other fields).

### Features

**MATLAB/Octave**

- Signal/image processing, FFT, filtering, matrix math, simulation, publication figure export
- Preserve original structure, centralize key parameters, add physical-meaning comments

**Python scientific stack**

| Library | Use |
|---------|-----|
| NumPy, SciPy, pandas | Data and numerical computing |
| matplotlib, seaborn | Publication-quality plots |
| scikit-learn | Classification, regression, clustering, dimensionality reduction |
| statsmodels | Linear models, time series, GLM |
| SymPy | Symbolic math |
| pymoo | Multi-objective optimization |
| simpy | Discrete-event simulation |
| QuTiP | Quantum optics / open quantum systems |
| pymatgen | Materials (structure, bands, DOS) |
| TimesFM | Time-series forecasting |
| NetworkX | Graphs and networks |
| Astropy | Astronomical / optical imaging style data |

**Literature and citations**

- Paper lookup: arXiv, PubMed, CrossRef, Semantic Scholar, OpenAlex
- Citation management: DOI → BibTeX, metadata extraction, citation validation
- Prefer PubMed / OpenAlex / Crossref over Google Scholar scraping (see SECURITY.md)

---

## 4. academic-figure-prompt — AI diagram prompts

Writes **detailed English prompts** for official image tools (Gemini, ChatGPT Images, Midjourney, DALL-E). It does not generate pixels and does not call any image API.

Two styles (ask if unspecified):

- **Classic** — white boxes, thin coloured borders, Okabe–Ito and other journal palettes
- **Pastel / modern ML** — white canvas, floating white panels, rounded type, pastel tokens

### Safety

- Prompt text only. No bash, no network, no LigphiDonk web app.
- You paste the prompt into an official image tool you already use. Never `api.keepgo.icu`.
- Conceptual diagrams only. Real data plots stay in `scientific-toolkit-skill`.
- See [SECURITY.md](SECURITY.md).

English localization of the SKILL.md files from [LigphiDonk/academic-figure-generator](https://github.com/LigphiDonk/academic-figure-generator) (MIT). That project's FastAPI app is not included.

---

## Install

Each skill uses the same layout (`SKILL.md` + `agents/` + `references/`).

### Cursor

Global install:

```bash
cp -r research-writing-skill ~/.cursor/skills/
cp -r office-academic-skill ~/.cursor/skills/
cp -r scientific-toolkit-skill ~/.cursor/skills/
cp -r academic-figure-prompt ~/.cursor/skills/
```

Project-only install (this repo):

```bash
mkdir -p .cursor/skills
cp -r research-writing-skill office-academic-skill scientific-toolkit-skill academic-figure-prompt .cursor/skills/
```

### Claude Code

```bash
cp -r research-writing-skill ~/.claude/skills/
cp -r office-academic-skill ~/.claude/skills/
cp -r scientific-toolkit-skill ~/.claude/skills/
cp -r academic-figure-prompt ~/.claude/skills/
```

### Codex

```bash
cp -r research-writing-skill ~/.codex/skills/
cp -r office-academic-skill ~/.codex/skills/
cp -r scientific-toolkit-skill ~/.codex/skills/
cp -r academic-figure-prompt ~/.codex/skills/
```

---

## Directory layout

```
skill-name/
├── SKILL.md          # Skill definition and usage
├── agents/           # Agent display metadata
└── references/       # Docs, scripts, templates
```

---

## Language and evidence rules

| Rule | Detail |
|------|--------|
| **Default English** | Explanations, manuscript prose, and slides are English unless the user asks otherwise |
| **Preserve source terms** | Titles, formulas, variables, model names, software commands, reference entries |
| **No fabricated data** | No invented DOI, authors, journals, experimental values, figure numbers, or conclusions |
| **Label sources** | Attach source labels to claims, parameters, quantitative results, datasets, and figures |

---

## Acknowledgments

Design of the upstream project drew on:

| Project | Notes |
|---------|-------|
| [zouchenzhen/thesis-defense-pptx-skill](https://github.com/zouchenzhen/thesis-defense-pptx-skill) | Editable defense PPTX from thesis materials |
| [K-Dense-AI/scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills) | Scientific agent skill collection |
| [tfriedel/claude-office-skills](https://github.com/tfriedel/claude-office-skills) | Office document skills (docx/pptx/pdf/xlsx) |
| [Gabberflast/academic-pptx-skill](https://github.com/Gabberflast/academic-pptx-skill) | Academic PPT conventions |
| [SNL-UCSB/paper-writing-skill](https://github.com/SNL-UCSB/paper-writing-skill) | Paper-writing craft principles |
| [LigphiDonk/academic-figure-generator](https://github.com/LigphiDonk/academic-figure-generator) | Conference-style AI figure-prompt templates (English localization in `academic-figure-prompt`) |

---

## License

[MIT License](LICENSE) (Copyright (c) 2026 [zLanqing]). See [NOTICE](NOTICE) for derivative notes.

Some bundled scripts under `scientific-toolkit-skill/references/scientific-skills/` retain their original licenses.
