---
name: academic-writing
description: Refine academic writing for high-impact peer-reviewed journals (e.g., IEEE, Nature/Science sub-journals, Elsevier, Springer, APA). Use this skill whenever a user asks to improve, polish, refine, edit, or proofread academic or research writing — including paper drafts, abstracts, introductions, methodology, results, discussions, or conclusion sections.
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

### Before Implementation

Infer from content (ask if ambiguous):

- **Section type**: Abstract, Introduction, Methodology, Results, Discussion, Conclusion, or mixed.
- **Edit depth**: "light edit / grammar only" → skip to Step 3.

### Step 1 — Identify key points

Extract the key points from the input — the ideas the reader must take away from this section.

For each candidate key point, verify:

- **Independent**: It cannot be subsumed by another key point. (It may relate to other points, but it carries its own distinct message.)
- **Necessary**: The reader needs it — it serves a clear function in the section's argument. You can articulate *why* the reader must know this.
- **Supported**: Evidence or reasoning backs it up. If a key point is asserted without support, flag it.

Separate key points from supporting details. Supporting details (explanations, evidence, examples, context) serve a key point — they are not key points themselves. If a paragraph contains no identifiable key point, it is either a supporting detail that has drifted from its parent, or content that should be cut.

Consult `reference/section-guide.md` to check whether expected key points are present or missing.

**Gate**: If key points are unclear, incomplete, or contradictory — **stop**. Do not proceed to organizing or polishing. Name exactly what is missing or ambiguous, and ask the author to clarify. A well-polished sentence that says the wrong thing is worse than a rough sentence that says the right thing.

### Step 2 — Organize for the reader

With key points confirmed, arrange them so the reader can absorb each one without friction.

**Order**: Each key point builds on what the reader already knows from the preceding points. The reader should never encounter a concept without the context to understand it. Where a key point establishes importance or motivation, it comes before the points it motivates.

**Hierarchy**: Nest supporting details under their key point. Each supporting detail directly serves its parent — if it doesn't, it belongs elsewhere or should be cut.

**Test**: Strip away all supporting details and read only the key points in sequence. Does the high-level argument hold? Can the reader follow the logical progression? If not, reorder.

Consult `reference/section-guide.md` for section-specific structural conventions (e.g., Introduction typically follows problem → gap → approach → contribution; Methodology follows problem formulation → method design → design rationale).

### Step 3 — Refine language

With key points identified and organized, refine *how* they are expressed. Two atoms govern this step:

**Precisely** — eliminate ambiguity. Every term, referent, and claim should have exactly one possible reading. Check: if two readers read this sentence, would they extract the same meaning?

**Efficiently** — eliminate waste. Every word, sentence, and paragraph must contribute to the reader's understanding of a key point. If it doesn't, remove it. If information appears in two places, keep it in the one place where the reader needs it most.

Consult the following references based on what you are refining:
- **Word choice** (selecting or replacing individual words and phrases) → `reference/word-choice.md`
- **Sentence and paragraph construction** (restructuring information flow, connectors, voice, tense, paragraph function) → `reference/sentence-construction.md`

### Step 4 — Output

1. **Refined text** as the primary output. Match input format (LaTeX in → LaTeX out; plain text in → plain text out). When input contains LaTeX, preserve all `\cite{}`, `\ref{}`, `\label{}`, equation environments, and custom macros exactly — edit only the prose.
2. **Change notes** — brief annotations for non-obvious changes (e.g., "Moved contribution statement before method overview to establish value earlier").
3. **Flags** — issues that require the author's input: missing citations (mark as **[citation needed]**), unsupported claims, logical gaps, information you chose not to invent.

## Constraints

**Don't assume. Don't hide confusion. Surface tradeoffs.**

- State your assumptions about the target audience, tone, and format explicitly. If uncertain, ask.
- If key points are unclear or the core message is ambiguous, stop. Name what's missing. Ask.
- Do not invent content. If something is missing, flag it — do not fabricate claims, results, or citations.
- Do not insert fancier vocabulary than what is needed. If the original word is correct and simple, keep it.
- Do not flatten the author's voice. Polish, not homogenize.
- When the user requests a light edit, respect it: fix grammar, spelling, and punctuation only.
