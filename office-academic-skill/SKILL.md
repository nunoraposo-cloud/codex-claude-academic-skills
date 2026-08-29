---
name: office-academic-skill
description: English-first academic Word and PowerPoint workflow for paper reading reports, thesis or group-meeting PPTs, editable DOCX/PPTX generation, Office file inspection, template matching, speaker notes, and layout quality checks. Use when the user asks to read papers into Word reports, create or polish PPT/PPTX, convert paper/thesis materials into slides, edit DOCX/PPTX, inspect Office files, or produce academic presentation/report deliverables. Preserve paper titles, formulas, variable names, software commands, and references.
---

# Office Academic Skill

## Scope

Use this skill for:

- Word reports from PDFs, DOCX files, arXiv papers, journal articles, theses, and manuscripts.
- English-first academic PPTs for literature reports, group meetings, courses, opening/midterm/defense presentations, and project presentations.
- Editable `.docx` and `.pptx` generation, inspection, repair, and style preservation.
- PPT template matching, native slide editing, speaker notes, and visual quality checks.

Do not use this skill for pure manuscript prose drafting without a Word/PPT deliverable; use `research-writing-skill` instead. Do not use it for MATLAB, Python analysis, statistics, or plotting unless those outputs are being inserted into Word/PPT.

## Language And Evidence

- Default to English for explanations, Word report prose, slide text, outlines, and speaker notes.
- Preserve titles, formulas, variables, model names, software commands, reference entries, and direct source labels as they appear in the source.
- If the user asks for Chinese (or another language), switch for that deliverable only.
- Distinguish `source text`, `figure/equation evidence`, `code or simulation results`, `inferred from context`, and `suggestion`.
- Do not invent DOI, authors, journal details, experiment values, figure numbers, section names, page numbers, or conclusions.
- Attach source labels to claims, parameters, quantitative results, formula explanations, datasets, figures, limitations, and novelty statements.

## Paper Reading To Word

Default output, unless the user asks otherwise:

1. An English report for reading, teaching, or presentation preparation.
2. Optional bilingual English–Chinese report only if the user asks for it.
3. Optional Markdown working notes if useful.

Before writing, build a source map:

- Title, authors, venue, year, DOI/arXiv if present.
- Section headings and page spans when available.
- Figures, tables, equations, datasets, hardware/software, and evaluation settings that support key claims.
- Uncertain or missing metadata marked as `not stated in the source`.

Use `references/report-structure.md` for the default report structure and evidence-label format.

For `.docx` creation or editing:

- Prefer structured headings, summary tables, figure/table placeholders, and source labels.
- Use Times New Roman, Calibri, or Arial for body text; use Microsoft YaHei or SimSun only when Chinese text is required.
- For existing academic/legal/business Word documents, make a new version or use tracked-change style edits rather than overwriting the original.
- For advanced DOCX operations, use `references/office-docx/ooxml.md`, `references/office-docx/docx-js.md`, and the scripts under `references/office-docx/`.

## Academic PPT Workflow

First clarify only the high-impact missing details:

- Purpose: literature report, group meeting, course report, opening/midterm/defense, project display, science communication, or other.
- Duration and slide count.
- Audience and evaluation criteria.
- Required template, school/company constraints, fonts, ratio, logo, sections, notes, or output format.
- Source files: paper, thesis, Word draft, data, MATLAB/Python/Origin figures, screenshots, old PPT, template.

If the user asks to proceed immediately, make reasonable defaults and state them briefly.

For research PPTs, use a concise structure:

1. Cover.
2. Research background and problem.
3. Related work or theoretical basis.
4. Method, model, system, or algorithm.
5. Experiment/simulation setup.
6. Results and analysis.
7. Comparison and discussion.
8. Contributions, limitations, and outlook.
9. Q&A.

For paper-reading PPTs, use:

1. Paper metadata.
2. Background.
3. Core problem.
4. Method framework.
5. Experiment setup.
6. Main results.
7. Contributions.
8. Limitations.
9. Possible improvements.
10. Relationship to the user's topic.

## Slide Quality Rules

- One core point per slide.
- Prefer action titles that state the conclusion, not vague topic labels.
- Figures, diagrams, tables, and formulas should carry the technical argument; avoid long paragraphs.
- Keep axes, units, legends, formulas, assumptions, data sources, and figure captions scientifically accurate.
- Use white or restrained academic backgrounds unless a supplied template requires otherwise.
- Limit colors and decoration; use color to direct attention to evidence.
- Avoid text overflow, image stretching, missing fonts, stale template text, bad navigation labels, and overlapping elements.

The `academic-pptx` repository was reviewed as an external reference. Because it marks its license as proprietary, do not copy its text into outputs or this skill. Use only general academic presentation principles: argument-first structure, action titles, evidence-led slides, and the ghost-deck test.

## PPTX Technical Work

For template-matched defense PPTs:

- Prefer copying native template slides and replacing content rather than rebuilding from blank slides.
- On Windows with Microsoft PowerPoint installed, PowerPoint COM can be used for cloning, export, and overflow inspection. These `.ps1` helpers are Windows-only and inert on macOS.
- Never modify the user's original PPTX directly. Work on a timestamped or versioned copy.
- Do not disable PowerPoint add-ins or change application settings unless the user explicitly approves in that task.

Useful bundled resources:

- `references/thesis-defense-pptx/scripts/` for thesis context extraction, template cloning, slide export, contact sheets, text scans, and overflow inspection.
- `references/office-pptx/` for OOXML-level PPTX inspection and editing.
- `references/office-docx/` for OOXML-level DOCX inspection and editing.

## Quality Gate

Before final delivery, verify what is feasible:

- For Word: inspect extracted text or package XML for missing text, broken images, table overflow, and source labels.
- For PPT: export or inspect slides, check page order, stale placeholders, text overflow, image aspect ratio, overlap, and readability.
- Report output file paths, source paths, extraction method, checks performed, and unresolved uncertainties.
