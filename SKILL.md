---
name: content-heuristics
description: Evaluate pasted content, a design screenshot, or a URL against Andrew Tipp's 12 heuristics for content design (Accessible, Accurate, Concise, Consistent, Discoverable, Ethical, Inclusive, Prioritised, Readable, Scannable, Specific, Useful). Shows recommended content improvements next to the original content in a table. Use when the user asks to evaluate, audit, or review content quality, UX writing, or page copy.
user-invokable: true
args:
  - name: target
    description: Content pasted inline, a screenshot, or a URL to evaluate (optional)
    required: false
---

Evaluate content against Andrew Tipp's 12 heuristics for content design (https://uxplanet.org/12-heuristics-for-content-design-f6d7ec989cb5) and show recommended improvements next to the original content in a table. Heuristics are guidelines, not hard laws — judge in context, but understand the rules before breaking them. Limit the evaluation to what is actually in front of you: do not assume context beyond the content itself.

## Input Handling

1. **Pasted content**: Evaluate the text directly.
2. **Design screenshot**: Read the image. Extract all visible copy — headings, body text, labels, buttons, links, error messages, alt-text hints, visual hierarchy — then evaluate that copy.
3. **URL**: Fetch the page. Use the main content (not boilerplate, cookie banners, or nav chrome unless it is problematic). Note the rendered heading hierarchy, link texts, alt text, and meta description when evaluable.

If no target is given, ask for one, or evaluate the content pasted in the most recent user message.

## The 12 Heuristics and Evaluation Criteria

Evaluate against each. Mark a heuristic **Pass**, **Issue**, or **Not evaluable** (when the input can't show it — e.g. sign-off processes, review plans, SEO metadata on a screenshot). Never fail content on something the input can't show.

1. **Accessible** — Content should be perceivable, understandable and usable for disabled people.
   - Are headings nested and tagged appropriately (H1 → H2 → H3)?
   - Does text have strong colour contrast (4.5:1) against its background?
   - Do images have appropriate alt text and avoid rendering text inside the image?
   - Does every link make sense in isolation, without duplicated link text for different destinations?
   - Do videos have closed captions and audio descriptions where appropriate?

2. **Accurate** — Information should be correct (and regularly reviewed).
   - Has any AI-generated content been validated by a human?
   - Has the content been signed off by relevant stakeholders?
   - Is there a plan to review and maintain the information?
   - From the content alone: flag internal contradictions, stale facts (dates, versions, prices), and typos.

3. **Concise** — Use the fewest words practically possible.
   - Have redundant words been removed?
   - Could the content be rewritten to convey the same information in fewer words?
   - Does every piece of information justify its inclusion?
   - Has anything been lost to oversimplification? (Never sacrifice clarity for brevity.)

4. **Consistent** — Follow organisation content guidelines.
   - Is the tone of voice consistent throughout?
   - Does the content follow style guidance consistently (capitalisation, numbers, terminology, punctuation)?
   - Are layouts and patterns consistent with similar types of content (e.g. every card, dialog, or error message built the same way)?

5. **Discoverable** — Users should be able to find and use your content no matter how they access it.
   - Is the content optimised for search (relevant keywords, meta title/description)?
   - Will it be easily found through navigation (labelled and organised where users expect)?
   - Is it accurately summarisable by AI assistants (clear front-loaded summaries)?

6. **Ethical** — Place user needs above organisation goals.
   - Does the content avoid dark patterns (fake urgency, hidden costs, confirm-shaming, forced continuity, tricky opt-outs)?
   - Are only fair behavioural nudges used?
   - Does it comply with privacy/data protection regulations and policies?

7. **Inclusive** — Design for everyone and reflect community diversity.
   - Can the content be used in different situations (low lighting, noisy environment, slow connection)?
   - Does it use inclusive language (avoiding bias by age, gender, ethnicity, ability)?
   - Are images and examples representative of community diversity?

8. **Prioritised** — Present the most important information first, then gradually reveal less important details.
   - Is the most important information prominent?
   - Is less important information revealed gradually (progressive disclosure, inverted pyramid)?
   - Is there a clear visual hierarchy guiding the eye in a logical order?

9. **Readable** — Content should be easy to read and understand for everyone.
   - Is it written in plain, everyday language?
   - Is the active voice used?
   - Are sentences short (under 25 words)?
   - Are acronyms and initialisms explained on first use?

10. **Scannable** — Format content so users can understand it without reading all of it (people read only ~28% of a page).
    - Are titles and headings in sentence case and descriptive?
    - Are paragraphs short (1–2 sentences)?
    - Is the purpose of every link clear on its own?
    - Is bold text used to highlight important details (sparingly — if everything is highlighted, nothing is)?
    - Are bullet points used for lists and tables for tabular data?

11. **Specific** — Be precise and avoid jargon, ambiguity or assumptions.
    - Is timing/quantity precise ("monthly", "read in 5 minutes", not "regularly", "quickly")?
    - Is ambiguity avoided ("we" is clear in context)?
    - Is jargon and buzzword use avoided, or explained?
    - Does it avoid assuming prior knowledge?

12. **Useful** — The purpose of content is to help users find information or complete a task.
    - Does the title and lead text make clear what users can expect to find and do?
    - Is the heading structure based on user needs and questions?
    - Is the next step in the journey clear (a visible call to action)?
    - Is the content kept minimal to reduce cognitive load?

## Evaluation Method

1. Read the full content (or screenshot) once as a user would, noting instinctive friction points.
2. Walk each heuristic criterion by criterion, collecting concrete findings with the exact original text quoted.
3. For each issue, write a specific, better rewrite — not generic advice. The improvement column should contain copy the user could paste in and ship.
4. Record the heuristic and the specific criterion violated for every finding.

## Output Format

### 1. Findings table

| Heuristic | Original content | Issue | Recommended improvement |
|---|---|---|---|
| Specific | "We will regularly update this page" | "Regularly" is vague; "we" is ambiguous | "We update this page on the 1st of every month" |

- Quote the original exactly (trim long passages; use «…»).
- One row per issue, ordered by heuristic number.
- Name the violated criterion in the Issue column.
- Rewrite improvements for copy; for structural issues (hierarchy, contrast, alt text) describe the concrete fix.

### 2. Pass summary

List heuristics with no findings, with one line on what made them pass.

### 3. Not evaluable

List heuristics/criteria the input couldn't reveal (e.g. "Accurate: sign-off/review processes — verify with the content owner"; "Discoverable: SEO metadata — not visible in screenshot"). Frame these as questions to check, not failures.

### 4. Top 3 priority fixes

The three changes with the biggest user impact, in order.

Keep the tone direct and practical. Remind the user that heuristics are guidelines — any deviation should be a choice, not an accident.
