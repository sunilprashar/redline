# 0012 — Tier decides the question asked, not a confidence score

Status: accepted · 2026-08-28

## Decision

There is no confidence number. Tier-one clause types are searched with a
recall-shaped question — does anything here resemble one of these, include
anything arguable — and tiers two and three with a precision-shaped one: flag
only what clearly and unambiguously does this. Which pass produced a candidate
decides whether hedged output survives.

## Alternatives

- **A self-reported score from the model.** The obvious reading of ADR-0006,
  and the reason this needed deciding: model-reported confidence is poorly
  calibrated, so the tier boundary would rest on a number that does not mean
  what it says.
- **Self-consistency across repeated samples** — flag when a clause appears in
  k of n runs. Genuinely calibrated and the most expensive option available.
  Worth revisiting if the recall pass proves noisy.

## Why

ADR-0006 spends generosity where harm is irreversible and protects the noise
budget everywhere else. That is a statement about what we ask, not about a
threshold we apply afterwards. Encoding it in the question removes the need to
trust a number, and makes the behaviour testable: a hedged tier-one candidate
survives because of the pass it came from, not because a score cleared a bar.

## Consequences

- At least two model passes per document, so cost and latency roughly double
  against a single call. That is the price of the tier split.
- Tier assignment now happens before the model call, not after it, since the
  tier determines which pass looks for a clause type.
- Adding a clause type means deciding which pass it belongs to, which is a
  visible edit rather than a threshold nudge.
