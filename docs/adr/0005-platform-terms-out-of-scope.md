# 0005 — Platform terms are out of scope

Status: accepted · 2026-08-28

## Decision

Version one reads brand deals and agreements. Platform terms of service leave
scope, superseding their inclusion in ADR-0002.

## Alternatives

- **Keep them with a second output shape** — flags and citations but no
  counter-offer, since nothing is negotiable. Rejected: one product with two
  output shapes, decided in the brief or discovered during build.
- **Keep them unchanged.** Not viable. A drafted counter-offer is one of six
  scoped features and nobody counter-offers to YouTube.

## Why

Every flag in this product ends in something the reader can do. Against a
take-it-or-leave-it document the only available action is to stop publishing
there, which is not a counter-offer and not advice we can give. A 20,000-word
ToS is also a different parsing and cost problem from an eight-page deal.

## Consequences

- Platform terms change unilaterally and can end a creator's income overnight.
  That is plausibly the largest risk in their working life and we are choosing
  not to look at it.
- `CONTEXT.md` keeps the term, marked out of scope, because creators will ask
  and the answer needs to be a decision rather than an oversight.
