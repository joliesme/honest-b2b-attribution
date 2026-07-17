# Dashboard Patterns

Structure and habits for a Power BI campaign influence dashboard that leadership trusts, with notes that transfer to any BI tool.

## The fiscal date table

Build one dedicated date table aligned to the company's fiscal calendar and relate every fact table through it. If the fiscal year starts in July, the date table encodes that once, and every visual inherits correct fiscal quarters without per-measure hacks. Mixing calendar and fiscal logic across measures is the quiet source of most "numbers don't tie" tickets.

## Layout that pre-answers objections

- **Headline card**: Campaign-Touched accounts in pipeline, with the methodology disclaimer directly beneath it. Adjacent, not in a tooltip, and not on page 6.
- **Funnel visual**: each stage labeled with its definition available in one click. Mutually exclusive counts only.
- **Cohort lag view**: exposure cohorts tracked over time, so slow-burn campaigns aren't misread as dead ones.
- **Match quality panel**: match rate, threshold used, validation sample result, unmatched percentage. This panel does more for credibility than any pipeline number on the page.

## Measure hygiene

- One measure per business concept, named in the report's vocabulary (e.g. `Campaign-Touched Accounts`), never duplicated with slightly different filters.
- Stage measures enforce exclusivity in DAX rather than trusting the source data to be clean.
- Every measure that embeds a judgment call (window length, threshold, precedence) gets a comment stating the decision and the date it was agreed.

## The habit that matters most

When a number changes methodology, annotate the dashboard and keep the old measure available for one cycle. Restated numbers without a visible restatement note read as manipulation even when they're improvements.
