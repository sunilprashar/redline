# 0006 — Generous in tier one, strict below it

Status: accepted · 2026-08-28

## Decision

Where a clause is irreversible — tier one in ADR-0004 — we flag on suspicion
and accept false positives. In tiers two and three we flag only on confidence
and accept misses.

## Alternatives

- **Generous everywhere.** A routine eight-page deal returns fourteen flags,
  and the licence grab is buried among warnings about payment schedules.
- **Strict everywhere.** Safer-looking, and worse: the day we miss a
  perpetuity clause the signer has read a clean report and signed.

## Why

The costs are not symmetric. A false positive costs the reader two minutes
and some trust. A false negative costs them their catalogue, and they never
find out we missed it. But trust is the product — a tool nobody believes is
not made safe by caution — so the generosity is spent only where the harm
cannot be undone, and the noise budget is protected everywhere else.

## Consequences

- We will flag standard licence grants that any reasonable deal contains.
  Experienced readers will call the product jumpy, and they will be right.
- Slow payment and scope creep — the commonest real complaints — will
  sometimes go unflagged.
- Tier assignment now carries the tuning, so a clause placed in the wrong tier
  is a severity bug, not a cosmetic one.
