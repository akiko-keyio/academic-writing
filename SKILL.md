---
name: academic-writing
description: Refine academic writing for high-impact peer-reviewed STEM journals (e.g., IEEE, Nature/Science sub-journals, Elsevier, Springer). Use this skill whenever a user asks to improve, polish, refine, edit, or proofread academic or research writing — including paper drafts, abstracts, introductions, methodology, results, discussions, or conclusion sections. Operates on an existing draft; if the input is only notes or an outline, ask for a prose paragraph first.
---

# Academic Writing

This skill takes an existing draft — at any stage from rough notes to near-final prose — and improves its argument structure, evidence, and language for the target reader.

## Principles

Every claim in a paper is either already accepted by the reader or not yet. Writing is the work of converting not-yet into accepted, one step at a time: the reader holds claim A, judges from their background that A implies B, and now holds B. 

A paper is the graph of these chains. A good one forms a **pipeline**: make the reader **care** enough to enter, **understand** each step, arrive **convinced** — all **effortlessly**. 

| Target           | Reader question         | The text must                                                                                                   |
| ---------------- | ----------------------- | --------------------------------------------------------------------------------------------------------------- |
| **Care**         | Why should I enter?     | Open at an unresolved tension the reader already holds; end at a claim that unlocks further reasoning or applications; the connection between them is not one the reader could derive alone. |
| **Understand**   | Can I follow each step? | Every inference lands inside the reader's background; recurse (insert intermediate claim) until it does. |
| **Convinced**    | Must I accept?          | Every unstated assumption is one the reader would accept; alternative explanations are addressed.               |
| **Effortlessly** | At what cost?           | Reader working memory is finite — only recently accepted claims stay accessible. Keep each next step close to what the reader currently holds. |

## Workflow

This workflow helps you systematically find and fix breaks in the author's narrative graph — places where the reader would stop caring, lose the thread, or remain unconvinced. Work in **Stage 0 → 1 → 2 → 3**:

- **Stage 0** — define the target reader
- **Stage 1** — extract what the draft says and map its argument structure
- **Stage 2** — check that every claim has sufficient evidence
- **Stage 3** — rewrite the prose based on the confirmed map

Advance only on the author's confirmation. Never skip stages.

If the author revises the draft in response to feedback, re-run from the earliest affected stage.

### Stage 0 — Define the Reader

Without knowing the reader's background, you can't judge which inferences they can make — so every later decision depends on this step.

Among readers who could plausibly care, pick the one with the weakest background as the baseline — enough depth for them is tolerable redundancy for stronger readers; the reverse fails. For standard STEM journal targets this baseline is a researcher in the same field but not your specific sub-area. Adjust upward for cross-disciplinary venues (Nature, Science, PNAS), downward for sub-specialty journals.

**Persistence.** Check for `<manuscript_directory>/.academic-writing/reader.md`. If it exists and `Confirmed: YES`, skip Stage 0 — report which profile is in use and proceed to Stage 1.

**If no profile exists**, propose one based on the draft's venue, terminology, and cited literature. Write to `<manuscript_directory>/.academic-writing/reader.md`:

```markdown
# Reader Profile

**Paper:** <title or short identifier>

**Who they are:** <one line>

**Background they reliably have:**
- <item>
- ...

Confirmed: NO
```

Ask the author to confirm or edit. On confirmation, flip to `Confirmed: YES` with a date stamp. Proceed to Stage 1.



### Stage 1 — Map the Argument

Build the argument map in `<manuscript_directory>/.academic-writing/argument-map.md` in two passes, each ending with a diagnose-and-confirm step.

**Pass 1 — paragraph skeleton.** Read what each paragraph currently says and distill it into one claim (P) — a single short sentence that captures the paragraph's point, not a summary of its content. If a paragraph makes two distinct claims, split it into two P's. Each P carries a role tag from `reference/section-guide.md` (which defines each section's pipeline role and expected structure). Leave sub-claims to Pass 2.

```markdown
## Introduction

### P1 [Context]: Autonomous drones must plan paths in real time.
### P2 [Problem]: Obstacle-rich environments make real-time planning intractable.
### P3 [Prior Work]: Sampling methods are fast but miss narrow passages.
### P4 [Approach]: A learned heuristic guides sampling toward feasible corridors.
### P5 [Contributions]: Corridor predictor, guided sampler, and benchmark suite.
```

After listing all P: **diagnose**. Are the right roles present and in a logical order for this section's pipeline role (see `reference/section-guide.md`)? Can the reader follow from each P to the next? Propose fixes and confirm with the author. Mark confirmed P's with ✓.

**Pass 2 — within-paragraph claims.** For each confirmed P, add `- **C**` sub-items — the steps the reader must follow to arrive at P.

```markdown
### P2 [Problem]: Obstacle-rich environments make real-time planning intractable. ✓
- **C1**: Collision checks dominate computation in dense scenes.
- **C2**: Exact methods scale exponentially with obstacle count.
- **C3**: Real-time budgets (< 50 ms) leave no room for exhaustive search.
```

After expanding each P: **diagnose** — can the target reader follow from each C to the next, and from the last C to P?

Two kinds of gap:
- **Can't follow** — a reasoning step the reader's background can't bridge → add an intermediate C now.
- **Won't believe** — the reader can follow the logic but would doubt the claim → mark it for Stage 2 (evidence needed).

Also flag: redundant C's, wrong order. Propose fixes. Confirm P-by-P.

### Stage 2 — Check the Evidence

Stage 1 confirmed the reasoning chain is followable. Now check a different thing: does the reader have enough reason to accept each claim?

Goal: every claim in the argument map has sufficient evidence to hold against a skeptical reader.

Walk the argument map and add **evidence** as sub-items beneath each C:

```markdown
- **C1**: [claim] ✓
  - E: [citation]
  - E: [own data / derivation]
  - ⚠️ [gap: what is missing]
```

For each claim, ask:
- Are the hidden assumptions ones the target reader would accept?
- Has the obvious counter-argument been addressed?

For key claims (contributions, main findings), additionally:
- Is the claim supported by at least two independent paths — different data, different method, or different angle?

Across the whole argument map:
- Which step is most likely to be rejected by the target reader, and has that step been given extra support?

**Flag gaps, never fabricate.** Identify what is missing and where — never invent a citation, number, or result to fill it. The author supplies the evidence; the agent localizes the need.

Ask the author which flags to address before moving to Stage 3.

### Stage 3 — Rewrite the Prose

Goal: rewrite the prose section by section based on the confirmed argument map. Make every claim frictionless to read.

**Sentences.** Anchor each sentence in what the reader just learned (known-first, new-last). One claim per sentence. Connectors (*however / therefore / moreover*) must encode real logical relations. Tense encodes commitment — past for observations, present for general claims.

**Words.** Prefer simple words to fancy ones (use, not utilize). Cut anything that doesn't advance an inference. Quantify the vague. Use technical terms by their precise definition. One concept = one word throughout the paper.

**Precision before efficiency** — fix ambiguity before cutting length.

Every confirmed key point must survive unchanged in meaning. If a rewrite would alter a claim, surface it as a Stage 2 issue instead.

Consult as needed: `reference/word-choice.md`, `reference/sentence-construction.md`, `reference/section-guide.md`.

## Constraints

- **Never fabricate.** No invented citations, data, or results — flag the gap, let the author fill it.
- **Never skip stages.** Every transition waits on the author's confirmation.
- **Never alter meaning.** Polish expression, not substance. If a rewrite changes a claim, surface it in Stage 2.
