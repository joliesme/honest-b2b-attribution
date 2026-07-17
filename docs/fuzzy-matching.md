# Fuzzy Matching: Ad Platform Companies to CRM Records

Ad platforms report company names as their data providers see them. Your CRM stores names as reps typed them. "Acme Pte. Ltd.", "ACME Singapore", and "Acme Corporation" are the same account, and exact matching will tell you they aren't.

## Pipeline

1. **Normalize both sides**
   - Lowercase everything
   - Strip legal suffixes: Pte Ltd, Pte. Ltd., Inc, Corp, LLC, GmbH, Co., Ltd, and their non-English equivalents
   - Strip punctuation and collapse whitespace
   - Move geographic qualifiers (Singapore, APAC, SEA) into a separate field rather than deleting them, since they help disambiguate later

2. **Fuzzy match on normalized names**
   A token-based similarity score (token sort ratio or similar) handles word-order differences. A threshold around **85 out of 100** has been the working balance in my use: high enough to avoid absurd pairs, low enough to catch real variants.

3. **Validate the threshold on a sample**
   Manually review 50 matched pairs and 50 near-misses just below threshold before trusting any number downstream. Tune from there. The right threshold depends on your name distribution; 85 is a starting point, not a law.

4. **Keep the match table inspectable**
   Store source name, CRM name, score, and match decision as a table anyone can open. Attribution credibility lives or dies on whether you can show your pairs when challenged.

5. **Report the unmatched remainder**
   The percentage of exposure data you could not match is part of the methodology disclosure. Hiding it means someone else discovers it.

## Edge cases that will bite you

- Subsidiaries and regional entities: decide upfront whether they roll up to the parent account, and apply it consistently.
- Rebrands and acquisitions mid-campaign: keep an alias table.
- Very short names ("NCS", "IBM") score high against wrong partners; add an exact-match-only rule for names under a length floor.
