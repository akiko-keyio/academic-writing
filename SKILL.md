---
name: academic-writing
description: Refine academic writing for high-impact peer-reviewed STEM journals (e.g., IEEE, Nature/Science sub-journals, Elsevier, Springer). Use this skill whenever a user asks to improve, polish, refine, edit, or proofread academic or research writing — including paper drafts, abstracts, introductions, methodology, results, discussions, or conclusion sections. Operates on an existing draft; if the input is only notes or an outline, ask for a prose paragraph first.
---

# Academic Writing

## First Principle

> **Communicate valuable and verifiable ideas, precisely and efficiently.**

| Atom            | Core question                                      | What it demands                                              |
| --------------- | -------------------------------------------------- | ------------------------------------------------------------ |
| **Communicate** | Is it impossible for the reader not to understand? | Write for the reader's understanding, not the author's discovery. Each point builds on what the reader already knows. |
| **Valuable**    | Why should the reader care?                        | The reader can see why each point matters before being asked to engage with its details. |
| **Verifiable**  | Can the reader check every claim?                  | Methods carry sufficient detail for reproduction. Conclusions follow from exhibited evidence — cited, measured, or reasoned. |
| **Precisely**   | Is misreading impossible?                          | Every expression maps to exactly one meaning.                |
| **Efficiently** | Is every element essential?                        | If not, remove it.                                           |

## Workflow

Identify the section type from the draft; ask the author if unclear. If multiple sections are provided, operate on one section at a time.

Work in Stage 1 → 2 → 3 in order.

**One stage per turn.** Complete exactly one stage per assistant turn, then stop and wait. Advance to the next stage only after the user explicitly confirms.

**Do not skip ahead.** Do not produce refined text at Stage 1 or Stage 2, even if the draft looks close to ready. A polished rewrite delivered before key points are confirmed fails the author's intent, regardless of how well the prose reads.

### Stage 1 — Establish key points

1. Consult `reference/section-guide.md` to determine the expected key points for this section type.

2. Extract the key points:

   - A key point is a clear sentence stating the main point or argument of the paragraph.
   - Strip away all supporting details (explanations, evidence, examples, and context); they are not key points themselves.
   - The function of each key point should be traceable to `section-guide.md`.

3. Verify each candidate key point:

   - **Independent**: It conveys a distinct message. (Check: It cannot be subsumed by another key point.)

   - **Necessary**: It serves a clear function in the section’s argument. (Check: You can articulate *why* the reader must know this.)

     If a candidate does not pass, return to step 2 and re-extract the key points.

4. Arrange the candidate key points in order:

   - Each key point should build on what the reader already knows from the preceding points.
   - The key points should follow the section’s functional progression as defined in `section-guide.md`.

**Response.** End the turn after Stage 1 with one of two outputs:

**A. Key points established.** Present the ordered key points as a numbered list. For each, note its function in the section (traceable to `section-guide.md`). Then ask: *"Do these key points match your intent? Confirm to proceed to Stage 2."* Do not proceed without explicit confirmation. Do not include refined prose.

**B. Verification blocked.** If Stage 1 cannot complete — a check fails, a required key point is missing, or the draft's intent is unclear — do not fabricate or guess. For each issue, communicate three things: **what** is wrong (the problematic span or the missing element), **why** it is a problem (which check fails, or which required point is missing), and **what you need from the author** to unblock. Phrase each issue in whatever way makes those three things clearest. A polished sentence that says the wrong thing is worse than a rough sentence that says the right thing.

### Stage 2 — Support key points

With the Stage 1 key points confirmed, check whether each is sufficiently supported.

1. For each key point, locate its supporting content in the draft.

   Support is any content that substantiates a key point — citations, data, experimental results, examples, reasoning chains, method details, comparisons, derivations.

2. Assess sufficiency.

   Support is sufficient when a skeptical reviewer at the target venue can check the claim without leaving the text: a cited source for claims about prior work; a pointer to the experiment, number, or derivation (with uncertainty where the claim is quantitative) for claims about this paper; an explicit reasoning chain for causal or mechanistic claims.

3. Flag every gap with one of:

   - **`[citation-need]`** — the claim depends on prior work and needs a reference (a fact about the literature, field consensus, or a prior result).
   - **`[evidence-gap]`** — the claim is about this paper's own work (empirical, methodological, or quantitative) but the text does not substantiate it at the level the claim demands. Covers both *no support shown* and *support shown but below threshold*; the diagnosis specifies which.
   - **`[logical-leap]`** — the claim follows from others by a reasoning step the reader cannot reconstruct. The missing piece is inference, not evidence.

**Response.** End the turn after Stage 2 with:

1. The ordered key points from Stage 1 (restated for reference).
2. Each flag with its tag and a one-line diagnosis: which key point it affects, and what specifically is missing.
3. Ask: *"Confirm to proceed to Stage 3. Flags will be carried forward with the refined text — they are not blockers."*

Stage 2 does not halt on flags. Flags are carried forward, not resolved here. Do not include refined prose.

### Stage 3 — Refine language

Refine *how* the key points and their support are expressed, in this order:

1. **Precisely** (first) — eliminate ambiguity. Every term, referent, and claim should have exactly one possible reading. If two readers would extract different meanings from a sentence, rewrite it. Fix precision before cutting anything — trimming text before clarifying meaning risks deleting essential words.

2. **Efficiently** (second) — eliminate waste. Every word, sentence, and paragraph must contribute to the reader's understanding of a key point. If it doesn't, remove it. If information appears in two places, keep it where the reader needs it most.

3. Consult references as needed:

   - **Word choice** (selecting or replacing individual words and phrases) → `reference/word-choice.md`
   - **Sentence and paragraph construction** (information flow, connectors, voice, tense, paragraph function) → `reference/sentence-construction.md`

4. Verify preservation. Confirm that every Stage 1 key point is still present and unchanged in meaning. Stage 3 refines language, not content; if you find yourself needing to change what the text claims, surface it as a Stage 2 flag instead of editing.

**Response.** End the turn with:

1. **Refined text** — the section rewritten, with all Stage 1 key points preserved in meaning.
2. **Flags** — Stage 2 flags carried forward (inline markers or a list), so the author can address them.
3. **Change notes** — brief annotations for non-obvious changes (e.g., merged sentences, restructured paragraphs, replaced terminology).

## Constraints

- **Do not invent content.** If something is missing, flag it — do not fabricate claims, results, or citations.
- **Do not inflate vocabulary.** If the original word is correct and simple, keep it.
- **Do not flatten the author's voice.** Polish, not homogenize.
