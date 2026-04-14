---
name: academic-writing
description: Refine academic writing for high-impact peer-reviewed STEM journals (e.g., IEEE, Nature/Science sub-journals, Elsevier, Springer). Use this skill whenever a user asks to improve, polish, refine, edit, or proofread academic or research writing — including paper drafts, abstracts, introductions, methodology, results, discussions, or conclusion sections.
---

# Academic Writing

## First Principle

> **Communicate valuable and verifiable ideas precisely and efficiently.**

| Atom            | Core question                                      | What it demands                                                                                                |
| --------------- | -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| **Communicate** | Is it impossible for the reader not to understand? | Follow the reader's cognitive path, not the author's discovery path. Bridge from known to unknown for readers. |
| **Valuable**    | Why should the reader care?                        | Establish importance before asking the reader to invest in details.                                            |
| **Verifiable**  | Can the reader check every claim?                  | Provide sufficient detail for reproduction. Conclusions follow logically from exhibited evidence.              |
| **Ideas**       | What must the reader know?                         | Identify the key points the reader must retain from this section.                                              |
| **Precisely**   | Is misreading impossible?                          | Every expression maps to exactly one meaning.                                                                  |
| **Efficiently** | Is every element essential?                        | If not, remove it. What remains appears once, in the right place.                                              |

## Workflow

Run Steps 1 → 2 → 3 in order. When the Step 1 Gate halts the workflow and the author supplies clarification or additional material, re-run from Step 1 with the new input integrated.

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
- Required key points for this section type are missing (per `reference/section-guide.md`).

On halt, do not proceed to Step 2 or Step 3. See **Response rules** below. A well-polished sentence that says the wrong thing is worse than a rough sentence that says the right thing.

### Step 2 — Support key points

With key points established and ordered, check whether each is sufficiently supported.

Support is any content that substantiates a key point — citations, data, experimental results, examples, reasoning chains, method details, comparisons, derivations. For each key point, ask: *would a skeptical reviewer be persuaded by the support provided?*

Flag every gap:

- **[citation needed]** — claim that should cite prior work.
- **Unsupported claim** — assertion the author must back with data, reasoning, or reference.
- **Logical leap** — step in reasoning the reader cannot bridge from what is shown.

Step 2 does not halt. Flags are surfaced in the final output; the author addresses them. Proceed to Step 3.

### Step 3 — Refine language

Refine *how* the key points and their support are expressed. Two atoms govern this step, applied **in order**:

**1. Precisely** (first) — eliminate ambiguity. Every term, referent, and claim should have exactly one possible reading. If two readers would extract different meanings from a sentence, rewrite it. Fix precision before cutting anything — trimming text before clarifying meaning risks deleting essential words.

**2. Efficiently** (second) — eliminate waste. Every word, sentence, and paragraph must contribute to the reader's understanding of a key point. If it doesn't, remove it. If information appears in two places, keep it where the reader needs it most.

Consult based on what you are refining:

- **Word choice** (selecting or replacing individual words and phrases) → `reference/word-choice.md`
- **Sentence and paragraph construction** (information flow, connectors, voice, tense, paragraph function) → `reference/sentence-construction.md`

**Verify** (closing check). Compare the refined text against the Step 1 key points list. Is every key point still present, with its intended meaning intact? If refinement dropped or distorted a key point, restore it before output.

## Response rules

Output depends on where the workflow stopped:

- **Halt at Step 1 Gate** → Output only the issues the author must clarify or supplement (missing key points, failed Independent/Necessary, incoherent ordering). No refined text.
- **Step 3 completed** → Output three items:
  1. **Refined text** — match input format; edit only the prose.
  2. **Change notes** — brief annotations for non-obvious changes.
  3. **Flags** — Step 2 support gaps and any remaining issues surfaced during refinement.

## Constraints

**Don't assume. Don't hide confusion. Surface tradeoffs.**

- State your assumptions about the target audience, tone, and format explicitly. If uncertain, ask.
- Do not invent content. If something is missing, flag it — do not fabricate claims, results, or citations.
- Do not insert fancier vocabulary than what is needed. If the original word is correct and simple, keep it.
- Do not flatten the author's voice. Polish, not homogenize.
