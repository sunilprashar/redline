# 0013 — What gets quoted is a span, not a sentence

Status: accepted · 2026-08-28 · amends ADR-0001

## Decision

Every flag quotes a **cited span**: the shortest contiguous run of source text
that contains the operative language supporting the flag, reproduced verbatim.
A span may cross sentence boundaries, may include a stem and its enumerated
sub-clauses, and may be shorter than a sentence. Verification is unchanged —
the span must appear verbatim in the source.

## Alternatives

- **A sentence, strictly.** ADR-0001's original wording. It fails on the most
  important clauses in the taxonomy: a licence grant is routinely written as a
  stem plus a lettered list, and no single sentence contains the grant.
- **The whole clause or section.** Always contains the operative language, and
  hands the reader a wall of text to search. A citation that large stops being
  a citation.

## Why

The guarantee in ADR-0001 is that the reader can check us in one search. That
survives a span and does not survive a sentence rule that either omits half a
grant or forces us to quote a page. "Shortest span containing the operative
language" keeps the check cheap while keeping the quotation honest.

## Consequences

- ADR-0001's wording changes from sentence to span. The guarantee itself —
  verbatim, checkable, or the flag is dropped — is untouched.
- "Shortest containing the operative language" is a judgment the model makes,
  so span quality becomes something the corpus has to assess by hand. A
  technically verbatim span that omits the operative words passes verification
  and still fails the reader.
- Offsets now describe a range that may span structural boundaries, so text
  handling has to preserve list and sub-clause structure, not just characters.
