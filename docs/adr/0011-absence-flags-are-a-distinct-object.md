# 0011 — An absence-flag is a distinct kind of object

Status: accepted, not yet built · 2026-08-28

## Decision

A flag raised because something is missing — no kill fee, no cure period, no
payment milestones — is presented as a visibly different object from a flag
that quotes a sentence, and is never shown as though it carried a citation.
Cited flags ship first; absence-flags follow.

## Alternatives

- **Leave absences out entirely.** ADR-0001's original position. No longer
  available: ADR-0010 names freelancers, and their best-documented harm is an
  absence.
- **Quote the nearest related sentence** — cite the payment section and note
  what it omits. Rejected: it reads as a citation for a claim the quoted text
  does not support, which is the exact failure ADR-0001 exists to prevent.
- **Show them identically to cited flags.** Simplest interface, and it
  silently weakens the guarantee the product is built on.

## Why

ADR-0001 makes a checkable citation the basis for trusting anything Redline
says. An absence cannot be checked that way — there is no sentence — so it has
to look different, or the reader learns that some citations are real and some
are not and stops trusting all of them. Keeping the two visibly separate is
what lets the guarantee survive contact with a clause type it cannot cover.

## Consequences

- ADR-0008's method for naming absences credibly on the clean-result screen
  extends into flags, and becomes load-bearing rather than an edge case.
- Until this ships, the product does not claim to cover freelancer payment
  protection. Copy must not run ahead of the build.
- Absence detection is the hardest unsolved problem here: proving a clause is
  missing means reading the whole document, not finding a match in it.
