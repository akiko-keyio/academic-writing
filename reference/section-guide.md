# Section Guide

This guide specifies the purpose and structure for every section of a STEM research paper.

---

## Title

A good title lets a reader scanning a journal page decide in seconds whether this paper is relevant.

**Aim for**: 8–15 words. Specific enough to convey the contribution, general enough to attract the right audience.

**Patterns that work**:
- *[Method/Finding]: [What It Achieves] for [Problem/Domain]*
- *[Descriptive phrase] for [Task/Application]*

**Avoid**: Method-name-only titles; question titles (unless genuinely investigative); hype ("Novel", "Revolutionary", "Towards Ultimate"); nested subtitles.

**Check**: Does a non-specialist in your subfield understand what problem the paper addresses?

---

## Abstract

150–250 words (verify venue limits). Entirely self-contained — no citations, no undefined acronyms.

**Structure** (one element per 1–2 sentences):
1. **Problem & importance** — what real-world or scientific problem exists
2. **Gap** — what current approaches fail to address
3. **Approach** — what this paper does (name the method or contribution)
4. **Key result** — at least one concrete quantitative outcome
5. **Significance** — why the result matters beyond this paper

**Avoid**: Opening with "In this paper, we…"; vague phrases ("has attracted growing attention"); results without numbers; claims not supported in the paper body.

**Check**: A reader who sees only the abstract knows the problem, the approach, and the main result.

---

## Introduction

Typically 1–2 pages. The most-read section after the abstract. Its job is to make the reader care and then show them what you did about it. In most STEM fields the introduction also carries the background and literature review; a separate "Related Work" section is mainly a computer-science convention. When a separate section is not used, integrate that material here.

**Structure**:

1. **Context** — establish the problem domain and its significance. Ground it in something concrete (a real-world need, a scientific question, a measurable gap). Avoid truisms ("X has made remarkable progress").
3. **Essential background** — include **only** the knowledge the reader needs to understand the problem and your approach: key concepts, definitions, theoretical frameworks. If extensive background is required, refer readers to reviews or foundational papers rather than reproducing it.
4. **Gap & prior work** — survey what others have tried and where they fall short. Organize by theme, not by paper: describe the collective approach → highlight key advances → identify the remaining gap. Synthesize rather than list: "Several approaches address X by leveraging Y (A; B; C). However, they share a common limitation…" Be fair — characterize prior work accurately; do not caricature.
5. **Your approach** — introduce the key idea at a high level. Why should it work where prior methods did not?
6. **Contributions** — list 2–4 specific, verifiable contributions ("We propose X that achieves Y", not "We study Z").
7. **Roadmap** (optional) — include only if the paper structure is non-standard.

**Avoid**: Overclaiming ("We are the first…" — verify, or soften with "To the best of our knowledge"); motivating a solution instead of a problem (start with why, not what); burying the contribution in vague language; laundry-list literature reviews ("A did X. B did Y. C did Z.").

**Check**: After reading the introduction, does the reader know what gap exists, what you did, and why it matters? For every group of cited prior work, can the reader see how your work differs?

---

## Data / Datasets / Materials

Common as a standalone section in Earth-, environmental-, remote-sensing-, and observational-science papers where the data pipeline is substantial enough to merit its own treatment, upstream of the methods that operate on the data. In other fields this content is folded into Experiments (Datasets) or Methods (Materials); the principles below apply either way.

**Structure**:
1. **Source descripti-on** — for each data product: provider, version, spatial/temporal resolution, coverage window. Name the document, DOI, or access point so the reader could request the same inputs.
2. **Quality control** — selection criteria, filtering thresholds, handling of missing or low-confidence values. State what is excluded and why.
3. **Preprocessing & integration** — transformations applied before downstream use (coordinate alignment, height normalization, unit conversion). When multiple sources are combined, describe the alignment strategy and the fusion rule (interpolation, Kriging, weighted mean, model-based merger).
4. **Train/test or calibration/validation splits** — if the data serve both model fitting and evaluation, declare the split explicitly. Independence between splits is a claim the reader must be able to verify.

**Avoid**: Reporting raw data volumes without context; skipping why subsets were excluded; hiding method-level decisions here (if a step is part of the model, move it to Methods).

**Check**: Could a reader obtain the same source products and reproduce the preprocessed inputs from what is written here?

---

## Methods / Methodology

The core technical section. Detail must be sufficient for an independent researcher to replicate the study.

**Structure**:
1. **Overview** — when the method involves multiple stages or the overall flow is not self-evident, open with one paragraph (+ optional pipeline/architecture figure) giving the high-level picture before any detail.
2. **Problem formulation / Setup** — define the problem formally; introduce notation, variables, and assumptions. For experimental sciences: describe the system, organism, or phenomenon under study.
3. **Method detail** — present components in logical order; each builds on the previous. For experimental work: materials, instruments, procedures step-by-step, with non-standard procedures flagged explicitly. For computational work: model design, algorithms, key equations.
4. **Design rationale** — explain *why* you made the choices you did, not just *what* they are.

**Equations & notation**:
- Motivate before, interpret after: "To capture X, we define: [equation]. Intuitively, this measures…"
- Number only equations you reference later.
- Define every symbol at or before first use.
- Stay consistent: pick conventions (e.g., bold lowercase for vectors, bold uppercase for matrices, calligraphic for sets) and hold them.

**Avoid**: Jumping into formalism without motivation; inconsistent notation; missing units or dimensionality; omitting details that block replication (reagent concentrations, software versions, hyperparameters).

**Check**: Could a competent researcher in your field reproduce this work from this section alone?

---

## Experiments / Evaluation

Typically 1.5–3 pages. This section proves the claims made earlier.

**Structure**:
1. **Research questions or hypotheses** (optional but strong) — "We design experiments to answer: (RQ1)… (RQ2)…"
2. **Datasets / Materials / Subjects** — name, size, source, domain, splits or sampling strategy, preprocessing. For lab work: sample preparation, controls, replicates.
3. **Baselines / Controls / Comparisons** — what you compare against and why. Ensure fairness (same data, same resources, same evaluation).
4. **Implementation / Procedure details** — hyperparameters, training/measurement protocols, hardware, runtime. State how key parameters were selected (grid search, pilot study, prior literature).
5. **Evaluation metrics** — what you measure and why it is appropriate. Report units.

**Avoid**: Comparing only against weak or outdated baselines; omitting variance/error information; hiding negative results.

**Check**: Is every claim in the contributions matched by an experiment here?

---

## Results & Analysis

Can be combined with Experiments or stand alone. This section reports what you found — objectively, organized for clarity.

**Principles**:
- **Report objectively** — present the findings derived from your data without interpretation or speculation. What the results *mean* belongs in the Discussion. Here, stick to what the data *show*.
- **Organize logically** — follow the order of your research questions, hypotheses, or methods. The reader should be able to map each result back to the question it answers. Use subheadings if multiple questions or experiments are involved.
- **Organize around figures and tables** — tables and figures are the backbone of the Results section. Introduce each one before it appears ("Figure 3 shows…"), ensure it is properly labeled with clear captions, and use the surrounding text to highlight key trends or comparisons — not to repeat every number the reader can already see.

**Structure**:
1. **Main result** — lead with the primary table or figure; walk the reader through the most important comparisons.
2. **Supporting results** — additional conditions, variables, or measures that reinforce or qualify the main finding.
3. **Robustness checks** (where applicable) — sensitivity analyses, ablations, replicates, or alternative analytical approaches that test whether the finding holds under different conditions.
4. **Unexpected or negative results** — report them honestly. Selective omission undermines credibility.

**Presenting data**:
- Report uncertainty: standard deviation, confidence intervals, or p-values as appropriate to the field.
- Use consistent decimal places across compared values.
- Tables: bold best result where convention allows; reference every table/figure in the text.
- Avoid redundancy between text and visuals — summarize trends in prose, leave details to the figure or table. Extensive raw data or supplementary results can go in an Appendix.

**Avoid**: Cherry-picking favorable subsets; overclaiming marginal differences that fall within noise; presenting a table or figure with no accompanying discussion; mixing interpretation into result statements.

**Check**: Can the reader trace every result back to a research question? For every number you highlight, is the surrounding text adding insight (trends, comparisons) rather than simply restating the figure?

---

## Discussion

Optional as a standalone section; some papers fold it into Results or Conclusion.

**Include when**: results raise questions worth exploring, limitations need honest treatment, or findings have broader implications.

**Structure**:
1. **Interpret findings** — what do the results mean? Go beyond restating them.
2. **Connect to literature** — how do findings confirm, contradict, or extend prior work cited earlier?
3. **Implications** — what do these results contribute to the field or to practice?
4. **Limitations** — be specific: "Our method assumes X, which may not hold when Y." Name the impact on conclusions. This signals intellectual honesty, not weakness.
5. **Future work** — concrete directions, not vague gestures. "Applying the calibration method to multi-modal sensing under field conditions" beats "Extending to other domains."

**Check**: Has every major limitation been stated, and does each have a clear scope of impact?

---

## Conclusion

Typically 0.5–0.75 pages. A concise exit, not a second abstract.

**Structure**:
1. One-sentence restatement of what was done and why.
2. Key findings (brief — the reader has seen the details).
3. Main takeaway or insight — the single message the reader should remember.
4. Limitations & future work (if no separate Discussion section).

**Avoid**: Repeating the methodology; introducing new information or evidence; grandiose claims ("This work will transform the field"); excessive hedging.

**Check**: If the reader remembers only the last paragraph, do they retain the right message?

---

## Appendix

Use an appendix for material that would interrupt the main narrative but is necessary for verification: long derivations, explicit formulae and symbol tables, algorithm pseudocode, extended tables, or supporting results that reinforce but do not carry a main claim.

**Structure**: one topic per appendix; label A, B, C in order of first reference from the body. Each appendix is self-contained — the reader should be able to land in it from a single pointer in the main text and understand it without reading neighboring appendices.

**Typical content**: full derivations skipped in Methods; complete notation tables; reagent or instrument specifications; ablations or sensitivity studies that do not belong in the main Results; raw or expanded figures.

**Avoid**: Orphaned appendices never referenced from the body (if no one needs it, cut it); duplicating content already in the body rather than extending it; introducing new claims that the body relies on — the body should stand alone.

**Check**: For every appendix, is there a pointer to it from the main text at the moment the reader needs it, and does the appendix deliver what the pointer promised?
