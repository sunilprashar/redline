# 0007 — Confident about the text, silent about the law

Status: accepted · 2026-08-28

## Decision

Redline states textual facts flatly: "this licence has no end date." It makes
no legal claims at any confidence — not enforceability, not whether a clause
would survive a challenge. Where the model is unsure a clause means what it
thinks, the flag is dropped rather than hedged.

## Alternatives

- **Hedge everything.** "May potentially limit some rights in certain
  circumstances" is safe, survives any challenge, and tells the reader
  nothing. It is the house style of products that confuse legal caution with
  vagueness.
- **Give legal conclusions confidently.** Most useful, and the precise claim
  the FTC sanctioned DoNotPay for.

## Why

The DoNotPay precedent constrains the category of claim, not the tone. A
textual claim can be checked against the sentence we quote, so it can be
stated plainly and the reader can catch us. A legal conclusion cannot be
checked by the reader at all, which is why we do not make one.

## Consequences

- Recall falls again. Uncertain-but-real flags are dropped where hedging would
  have kept them, compounding the same trade in ADR-0001.
- "Is this legal?" and "will this hold up?" are the questions signers most
  want answered, and the product will visibly refuse them.
- The counter-offer must be written as a preference, not as legal advice.
