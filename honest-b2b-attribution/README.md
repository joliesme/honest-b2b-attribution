# Honest B2B Attribution

A working methodology for reporting campaign influence in enterprise B2B, where sales cycles run six to eighteen months, buying committees have a dozen people, and last-click attribution is a polite fiction.

I built this running campaign analytics for enterprise infrastructure products across APAC. It exists because I sat in the meeting where marketing's "sourced pipeline" number didn't match sales' number, and I decided I'd rather report a smaller figure that survives scrutiny than a bigger one that doesn't.

## The core position

**Report influence, not causation.** In enterprise B2B you can rarely prove that a campaign caused a deal. You can prove that an account was exposed to a campaign and later entered pipeline. So say that, in those words, and build the whole reporting stack around vocabulary that stays true under cross-examination.

This costs you something upfront. The number is smaller and the label is humbler. What you get back is that sales stops disputing your reports, finance starts citing them, and when you do show growth it means something.

## What's in this repo

| Doc | Contents |
|---|---|
| [docs/vocabulary.md](docs/vocabulary.md) | The "Campaign-Touched" framing, and why "sourced" and "influenced revenue" cause fights |
| [docs/funnel-definitions.md](docs/funnel-definitions.md) | Mutually exclusive MQL/SQL definitions and the precedence rules that keep counts clean |
| [docs/fuzzy-matching.md](docs/fuzzy-matching.md) | Matching ad-platform company names to CRM records: normalization, thresholds, validation |
| [docs/dashboard-patterns.md](docs/dashboard-patterns.md) | Power BI structure, the fiscal date table, and the disclaimer placement that builds trust |

## Who this is for

Marketers who own reporting in long-cycle B2B and are tired of choosing between numbers that impress and numbers that hold. Everything here is tool-agnostic in principle; the implementation notes assume Power BI plus a standard CRM export because that's the stack I run it on.

## What this is not

It's not multi-touch attribution modeling, and it deliberately avoids revenue-credit allocation ("this campaign gets 23% of this deal"). Those models produce precise-looking numbers from arbitrary assumptions, and precision without accuracy is how marketing loses the room.
