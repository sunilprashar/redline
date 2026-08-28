# 0004 — Severity is magnitude as the document states it

Status: accepted · 2026-08-28 · amended by ADR-0010

## Decision

Flags are ranked by magnitude drawn from the text itself — the length of a
term, the breadth of a grant, the size of a stated penalty — with
irreversibility breaking ties between clauses of similar size. The ranking
below replaces the one in `research/summary.md`.

Tier one: IP assignment and licence scope, exclusivity, perpetuity, morality
and conduct termination, and absent payment protection — no kill fee, no
milestones, no late-payment term (added by ADR-0010). Tier two: unilateral amendment, auto-renewal,
arbitration. Tier three: payment terms, deliverables, approval rights.

## Alternatives

- **Estimated harm.** Rank by what a clause will actually cost. Rejected: the
  figure is not in the document, and inventing one breaks the standing rule
  that we state only what the text says.
- **Probability.** Rank by how often a clause fires. Puts late payment above a
  perpetual licence, which inverts the risk for a first-time signer.
- **Inherit the research ranking.** It was built across gym members,
  borrowers, and retail employees. Personal guarantees barely appear in brand
  deals.

## Why

A reader can check stated magnitude against the sentence we quote: the term
says three years, the grant says worldwide, the penalty says €10,000.
Estimated harm cannot be checked against anything. Irreversibility earns the
tiebreak because signing is the last moment this reader has any say.

## Consequences

- This ranking is our judgment, not the research's. It is sourced to
  nothing in the folder and the brief must say so.
- Exclusivity is tier one despite appearing nowhere in the research — it was
  dropped for budget, not found unimportant.
- Scope creep still ranks low. Users will notice a common annoyance is not at
  the top.
- Absent payment protection is the one tier-one entry with no sentence to
  quote. It is presented under ADR-0011 and ships after the cited flags.
