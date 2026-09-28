# content-heuristics

Evaluate content against Andrew Tipp's 12 heuristics for content design
([article](https://uxplanet.org/12-heuristics-for-content-design-f6d7ec989cb5)) and get concrete,
paste-ready improvements shown next to the original copy.

## How to use

Give the skill one of:

- **Pasted content** — any copy, no matter how short (an error message, a landing page, an email).
- **A design screenshot** — all visible copy is extracted and evaluated.
- **A URL** — the page's main content is fetched and evaluated.

Example: "Run content-heuristics on this page: https://example.com/pricing"

## What it checks

All 12 heuristics, each with its concrete evaluation criteria from the article:

1. **Accessible** — headings, contrast, alt text, self-explanatory links
2. **Accurate** — validated, signed off, reviewed (contradictions and stale facts from the content)
3. **Concise** — fewest words practically possible, without losing clarity
4. **Consistent** — tone, style, and patterns
5. **Discoverable** — search, navigation, AI summarisability
6. **Ethical** — no dark patterns; user needs above organisation goals
7. **Inclusive** — works in different situations; inclusive language and representation
8. **Prioritised** — most important information first; progressive disclosure
9. **Readable** — plain language, active voice, sentences under 25 words
10. **Scannable** — sentence-case headings, short paragraphs, clear links, bullets and tables
11. **Specific** — precise, no jargon, no ambiguity, no assumptions
12. **Useful** — clear purpose, needs-based headings, obvious next step

## Output

1. A table: heuristic → original content → issue → recommended improvement (one row per issue).
2. A pass summary of what already works.
3. Items not evaluable from the given input, phrased as questions to check — never failures.
4. The top 3 priority fixes.

Evaluation is limited to what is actually in front of you: heuristics are guidelines, not laws.
