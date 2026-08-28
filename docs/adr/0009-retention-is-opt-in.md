# 0009 — Retention is opt-in, and the path is published

Status: accepted · 2026-08-28

## Decision

Document text is not retained after analysis by default. The saved library is
opt-in per document. We publish which inference provider sees the text and
whether it is trained on.

## Alternatives

- **Retain by default.** The library works out of the box and gets better with
  every deal. It also means we hold every signer's confidential contracts.
- **Say nothing about the provider.** Standard practice, and the reason
  confidentiality is a named complaint about using a chatbot for this.

## Why

Nearly every supplier agreement makes its own terms confidential. A signer who uploads
one is sending it to a third-party inference provider through OpenRouter and,
by default, storing it with us — potentially breaching the clause on page two
while reading page four. The research names confidentiality as one of two
recurring complaints about the free alternative; retaining by default would
reproduce that exposure and add persistence a chatbot does not have.

## Consequences

- The saved library is no longer a default experience, which weakens the
  repeat-user story in ADR-0003. History now costs the signer a decision per
  document.
- The OpenRouter provider choice becomes a product-facing commitment, not an
  implementation detail: a no-training route is now a requirement.
- Publishing the path invites comparison with competitors who say nothing.
