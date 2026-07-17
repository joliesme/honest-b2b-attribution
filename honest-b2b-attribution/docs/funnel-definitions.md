# Funnel Definitions

The most common reporting bug in B2B marketing is double counting: the same lead appearing in both the MQL and SQL totals, which inflates the funnel and eventually gets caught.

## Mutually exclusive stages

Each lead is counted in exactly one stage per reporting period. The precedence rule I use: count the lead at the **highest stage reached within the period**. A lead that became an MQL in April and an SQL in May appears in April's MQL count and May's SQL count, never in both columns of a cumulative view.

Write the precedence rule in the dashboard legend. When a stakeholder recalculates by hand and gets a different number, the written rule turns a credibility fight into a definitions conversation.

## Stage definitions worth writing down

- **Exposed**: account matched to campaign delivery data (see fuzzy-matching.md).
- **Engaged**: exposed, plus a tracked action attributable to a person at the account.
- **MQL**: meets the scoring threshold agreed with sales, timestamped by the date the threshold was crossed.
- **SQL**: accepted by sales, timestamped by sales' acceptance, not marketing's handoff. Using sales' own timestamp removes their most common objection.
- **Opportunity**: standard CRM definition; don't invent a marketing version.

## Reporting lag honestly

Enterprise funnels have lag measured in months. Report each cohort against its own timeline (exposure month, then conversion by month N) rather than judging last month's campaign by this month's pipeline. Cohort views are the difference between "the campaign failed" and "the campaign is four weeks into a twelve-week lag."
