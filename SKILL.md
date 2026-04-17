---
name: academic-writing
description: Refine academic writing for high-impact peer-reviewed STEM journals (e.g., IEEE, Nature/Science sub-journals, Elsevier, Springer). Use this skill whenever a user asks to improve, polish, refine, edit, or proofread academic or research writing — including paper drafts, abstracts, introductions, methodology, results, discussions, or conclusion sections. Operates on an existing draft; if the input is only notes or an outline, ask for a prose paragraph first.
---

# Academic Writing

## Principle

> **Make a skeptical reader care, understand, and believe — effortlessly.**

| Target         | The text must                                                |
| -------------- | ------------------------------------------------------------ |
| **Care**       | The reader sees why each point matters before being asked to engage with its details. |
| **Understand** | Each point builds on what the reader already knows — from background or from earlier in the text. |
| **Believe**    | Every claim is traceable to evidence, method, or reasoning.  |

*Effortlessly* modifies all three: one meaning per sentence, every element essential.

## Workflow

Identify the section type from the draft; ask if unclear. If multiple sections are provided, operate on one at a time in the paper's natural order: abstract → introduction → related work → methods → results → discussion → conclusion.

Work in **Stage 1 → 2 → 3, one stage per turn**. Advance only on the author's explicit confirmation. Do not produce refined prose before Stage 3 — a polished rewrite delivered before key points are confirmed fails the author's intent regardless of how well it reads.

If the author revises the draft in response to feedback, re-run from the earliest affected stage.

### Stage 1 — Establish key points

A key point is a single-sentence statement of what a paragraph is arguing. Supporting details (evidence, examples, context, explanation) are not key points — they serve key points.

1. Consult `reference/section-guide.md` for the expected key points and their functional order for this section type.
2. Extract candidate key points from the draft, stripping supporting detail.
3. Check each candidate:
   - **Atomic** — expresses one argumentative move only (no merged context + gap, gap + approach, or claim + justification).
   - **Independent** — conveys a distinct message; not subsumed by another key point.
   - **Necessary** — serves a clear function in the section's argument; you can state *why* the reader must know this.
4. Check the ordered set:
   - **Complete** — all key points required for this section type (per `section-guide.md`) are present.
   - **Coherent** — read in order, each point builds on the previous; the argument progresses without logical gaps.

Stage 1 is diagnostic — surface every problem you find rather than paper over them to advance.

**Response.** Present the ordered key points as a numbered list with each point's function, then ask the author to confirm the set matches their intent before Stage 2. If any check fails, a required point is missing, or the draft's intent is unclear, surface each issue with **what** is wrong (the span or missing element), **why** it fails (which check, or which expected point is absent), and **what you need** from the author. Do not guess or fabricate.

### Stage 2 — Support key points

For each confirmed key point, check whether its support in the draft is sufficient for a skeptical reviewer at the target venue to verify without leaving the text:

- Claims about prior work → a citation.
- Claims about this paper's own work (empirical, methodological, quantitative) → a pointer to the experiment, number, or derivation, with uncertainty where the claim is quantitative.
- Causal or mechanistic claims → an explicit reasoning chain.

Flag every gap with one tag:

- **`[citation-need]`** — claim depends on prior work and needs a reference.
- **`[evidence-gap]`** — claim is about this paper's own work but is unsupported or under-supported in the text; specify which.
- **`[logical-leap]`** — claim follows from others by a reasoning step the reader cannot reconstruct. The missing piece is inference, not evidence.

**Response.** Restate the ordered key points for reference, then list each flag with its tag, the key point it affects, and what specifically is missing. Ask the author to confirm before Stage 3; flags travel forward with the refined text and are not blockers.

### Stage 3 — Refine language

Refine *how* key points and their support are expressed, in this order:

1. **Precisely** — eliminate ambiguity. If two readers could extract different meanings from a sentence, rewrite it. Fix precision before cutting; trimming before clarifying risks deleting essential words.
2. **Efficiently** — eliminate waste. Every word, sentence, and paragraph must contribute to the reader's understanding of a key point. If it doesn't, remove it. If information appears twice, keep it where the reader needs it most.

Consult references as needed:
- **Word choice** → `reference/word-choice.md`
- **Sentence and paragraph construction** (flow, connectors, voice, tense, paragraph function) → `reference/sentence-construction.md`

Verify preservation: every Stage 1 key point must remain present and unchanged in meaning. If refining the language would require changing what the text claims, stop and surface it as a Stage 2 flag instead.

**Response.** Return three items:
1. **Refined text** — the section rewritten, Stage 1 key points preserved.
2. **Flags** — Stage 2 flags carried forward (inline or listed) for the author to address.
3. **Change notes** — brief annotations for non-obvious changes only (merged sentences, restructured paragraphs, replaced terminology). Skip obvious cleanups.

## Constraints

- **Do not invent content.** If something is missing, flag it — do not fabricate claims, results, or citations.
- **Do not inflate vocabulary.** If the original word is correct and simple, keep it.
- **Do not flatten the author's voice.** Polish, not homogenize.
