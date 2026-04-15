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

Run Steps 1 → 2 → 3 in order. On re-entry:

- If Step 1 halted and the author supplies clarifying material, re-run from Step 1 on the combined input.
- If the author returns with Step 2 flags addressed and key points unchanged, re-run from Step 2.

A section is done when Step 1 passes, no flags remain, and Step 3 yields no further meaning-preserving changes.

### Step 1 — Establish key points

Extract the key points — the ideas the reader must take away from this section — and verify they form a coherent argument.

**Per-point verification**. Each candidate key point must pass:

- **Independent**: It carries a distinct message, not subsumed by another key point. (It may relate to other points, but it is not redundant with them.)
- **Necessary**: The reader needs it — it serves a clear function in the section's argument. You can articulate *why* the reader must know this.

Separate key points from supporting details. Supporting details (explanations, evidence, examples, context) serve a key point — they are not key points themselves. If a paragraph contains no identifiable key point, it is either a supporting detail that has drifted from its parent, or content that should be cut.

**Set-level verification**. Arrange the candidate key points in order, strip away all supporting details, and read only the key points in sequence:

- **Coherent**: Each key point builds on what the reader already knows from the preceding points. The argument progresses without logical gaps. Where a key point establishes importance or motivation, it comes before the points it motivates.

Consult `reference/section-guide.md` to check whether the expected key points for this section type are present or missing, and whether the ordering matches the section's structural convention (e.g., Introduction typically follows problem → gap → approach → contribution).

**Gate**. Halt if any of the following holds:

- A key point fails **Independent** or **Necessary**.
- The ordered set is not **Coherent** — the argument does not progress, contradicts itself, or skips a logical step the reader cannot bridge.
- Required key points for this section type are missing.

On halt, do not proceed to Step 2 or Step 3 and do not produce refined text. For each issue the author must resolve, communicate three things: **what** is wrong (the span or the missing element), **why** it is a problem (which check fails, or which required point is absent), and **what you need from them** to unblock. Phrase each issue however makes those three things clearest. A well-polished sentence that says the wrong thing is worse than a rough sentence that says the right thing.

### Step 2 — Support key points

With key points established and ordered, check whether each is sufficiently supported.

Support is any content that substantiates a key point — citations, data, experimental results, examples, reasoning chains, method details, comparisons, derivations. Support is sufficient when a skeptical reviewer at the target venue can check the claim without leaving the text: a cited source for claims about prior work; a pointer to the experiment, number, or derivation (with uncertainty where the claim is quantitative) for claims about this paper; an explicit reasoning chain for causal or mechanistic claims.

Flag every gap:

- **`[citation-need]`** — the claim depends on prior work and needs a reference (a fact about the literature, field consensus, or a prior result).
- **`[evidence-gap]`** — the claim is about this paper's own work (empirical, methodological, or quantitative) but the text does not substantiate it at the level the claim demands. Covers both *no support shown* and *support shown but below threshold*; the diagnosis specifies which.
- **`[logical-leap]`** — the claim follows from others by a reasoning step the reader cannot reconstruct. The missing piece is inference, not evidence.

Step 2 does not halt; flags travel with the final output for the author to address.

### Step 3 — Refine language

Refine *how* the key points and their support are expressed **in order**:

**1. Precisely** (first) — eliminate ambiguity. Every term, referent, and claim should have exactly one possible reading. If two readers would extract different meanings from a sentence, rewrite it. Fix precision before cutting anything — trimming text before clarifying meaning risks deleting essential words.

**2. Efficiently** (second) — eliminate waste. Every word, sentence, and paragraph must contribute to the reader's understanding of a key point. If it doesn't, remove it. If information appears in two places, keep it where the reader needs it most.

Consult based on what you are refining:

- **Word choice** (selecting or replacing individual words and phrases) → `reference/word-choice.md`
- **Sentence and paragraph construction** (information flow, connectors, voice, tense, paragraph function) → `reference/sentence-construction.md`

**Verify**. Confirm that every Step 1 key point is still present and unchanged in meaning. Step 3 refines language, not content; if you find yourself needing to change what the text claims, surface it as a Step 2 flag instead of editing.

## Response

Output depends on where the workflow stopped:

- **Halt at Step 1 Gate** → the halt output described in Step 1, nothing else.
- **Full pass completed** → three items:
  1. **Refined text**
  2. **Flags** — the Step 2 output.
  3. **Change notes** — brief annotations for non-obvious changes.

## Constraints

- **Do not invent content.** If something is missing, flag it — do not fabricate claims, results, or citations.
- **Do not inflate vocabulary.** If the original word is correct and simple, keep it.
- **Do not flatten the author's voice.** Polish, not homogenize.
