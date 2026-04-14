# academic-writing

A portable skill for refining academic writing — paper drafts, abstracts, introductions, methods, results, discussions, conclusions — aimed at high-impact peer-reviewed journals (IEEE, Nature/Science sub-journals, Elsevier, Springer, APA).

The skill is a self-contained set of instructions and references. It can be loaded into any AI assistant or agent framework that supports Markdown-based skills, or consulted directly as a writing guide by a human author.

## Guiding principle

> Communicate valuable and verifiable ideas precisely and efficiently.

## Usage

Provide a draft section in plain text, Markdown, or LaTeX, and ask for a refinement:

> "Refine this methodology section for an Elsevier journal: …"

For a surface pass only, add `light edit — grammar and punctuation only` to skip the structural review.

## Files

| File | Purpose |
| --- | --- |
| `SKILL.md` | The workflow (4 steps: identify key points → organize → refine language → output) plus constraints. |
| `reference/section-guide.md` | Per-section expectations (Title, Abstract, Intro, Methods, Experiments, Results, Discussion, Conclusion). |
| `reference/word-choice.md` | Word-level guidance: fancy→simple, filler, weak verbs, hedging, acronyms. |
| `reference/sentence-construction.md` | Sentence- and paragraph-level guidance: flow, connectors, voice, tense, paragraph function. |

## Output

1. Refined text — input format preserved (LaTeX in → LaTeX out).
2. Change notes for non-obvious edits.
3. Flags for missing citations, unsupported claims, or logical gaps.
