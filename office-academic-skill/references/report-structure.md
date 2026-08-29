# Literature Report Structure

Use this structure when generating literature report documents from academic papers.

## Default English Report

Title page:
- Paper title
- Authors
- Venue and year
- DOI, arXiv, URL, or source file
- Report generation date

1. Executive Summary
- Research question
- Core method
- Main finding
- Why it matters
- Evidence label for each key point

2. Reading Map
- Suggested reading order
- Important sections, figures, tables, and equations
- What to focus on when preparing a group meeting or presentation

3. Background and Motivation
- Field context
- Unsolved problem or limitation in prior work
- Paper's stated objective

4. Method
- Overall framework
- Core model, algorithm, experiment workflow, or theoretical derivation
- Formula list with variable definitions, units, and assumptions
- Implementation details if present

5. Experiments or Evidence
- Dataset/sample/device/software/environment
- Parameter settings
- Baselines or controls
- Evaluation metrics

6. Results
- Key quantitative results
- Figure/table-by-figure/table interpretation
- What each result supports
- Any contradictory or weak evidence

7. Contributions and Novelty
- Contribution claimed by the authors
- Evidence from the paper
- Whether the novelty is methodological, experimental, theoretical, application-oriented, or system-level

8. Limitations
- Limitations stated by the authors
- Limitations inferred from scope, assumptions, dataset, sample size, metrics, or missing ablation
- Label inferred points clearly

9. Reproducibility
- Required data, code, instruments, software, versions, parameters, and steps
- Missing details that prevent reproduction

10. Relationship to User Topic
- Directly reusable ideas
- Cautions before reuse
- Possible extension experiments or simulations

11. Presentation Notes
- 5-minute version
- 10-minute version
- Likely questions from supervisor or audience

12. Reference Trace Table
- Claim
- Source location
- Evidence type: text, equation, figure, table, experiment
- Confidence: high, medium, low

## Optional Chinese Report

Produce a Chinese-language report **only if the user asks**. Use the same intellectual structure. Preserve English titles, model names, software names, formulas, variable symbols, datasets, and cited reference names.

Recommended Chinese headings when that mode is requested:
- 文献信息
- 一页式摘要
- 阅读路线
- 研究背景与问题
- 方法与模型
- 实验/仿真/数据设置
- 结果与图表解读
- 创新点与贡献
- 局限性与边界条件
- 可复现要点
- 与用户课题的关系
- 汇报讲稿要点
- 原文依据索引表

## Evidence Label Format

Preferred:
- `Source: Section 2.1, p. 3`
- `Source: Methods, pp. 4-5, Eq. (3)`
- `Source: Results, Fig. 5 and Table 2`
- `Source: Discussion, p. 9`

If exact location is unavailable:
- `Source: page number not given; see Results paragraph about Fig. 4`
- `Source: PDF text extraction missed section numbers; see paragraph under the table on p. 6`

Inference labels:
- `Inferred: based on experimental setup and missing ablation`
- `Suggestion: possible follow-up simulation direction; not a source conclusion`

## Quality Checklist

Before final delivery:
- The requested report(s) exist and open.
- Text is readable (no garbling).
- Each key conclusion has a source label.
- Quantitative values match the paper.
- Figures, tables, and equations are not misnumbered.
- Inferred comments are not mixed with original claims.
- The report notes missing information honestly.
- The final answer lists exact output paths and verification.
