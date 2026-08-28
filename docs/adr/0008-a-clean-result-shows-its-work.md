# 0008 — A clean result shows its work

Status: accepted · 2026-08-28

## Decision

When a document contains nothing worth flagging, Redline names the tier-one
clauses it searched for and did not find — "no exclusivity clause", "no
perpetual grant", "licence ends with the term" — rather than reporting that
nothing was found.

## Alternatives

- **"No significant risks found."** Honest and unbelievable. The reader
  assumes we did not look properly, and it is also the screen where a miss
  does the most damage.
- **Always find something.** Guarantees the product feels valuable and
  destroys it within a month, because a tool that always finds problems stops
  being read.

## Why

Most documents are fine, so the clean result is a common screen, not an edge
case. Naming specific absences converts an empty result into a finding the
reader can check against their own document in a minute. It also makes our
coverage legible: the reader learns what we looked for, which is the only way
they can judge what we might have missed.

## Consequences

- **This is the one screen where ADR-0001 does not hold.** An absence has no
  sentence to quote. The citation guarantee covers every flag we raise and
  cannot cover a clause that is not there.
- Consequently the tier-one checklist becomes a published claim about
  coverage. Adding a clause type to it is a change to what we promise.
