# 0001 — Every flag cites its source

Status: accepted · 2026-08-28 · amended by ADR-0013 (span, not sentence)

## Decision

Every risk flag carries the exact sentence from the uploaded document it came
from, quoted verbatim and shown to the reader. A flag whose source sentence
cannot be produced is not displayed. That is a bug, not a degraded result.

## Alternatives

- **Let the model describe risks in its own words.** Fluent, tolerant of messy
  input, and the shape of every free chatbot answer — and the reader has no way
  to tell a real clause from a plausible one.
- **Cite loosely** — a heading, a page number. Cheap, but it hands the reader a
  haystack and calls it a citation.
- **Quote, but drop the citation when extraction fails.** Keeps recall up. It
  also makes the weakest flags the unverifiable ones, which is backwards.

## Why

A reader who does not trust us can check us. Every claim points at text they
can find in their own document, so verification costs one search, not one
lawyer. Fabrication becomes visible rather than persuasive: a flag citing a
sentence that isn't there is a defect anyone can spot.

## Consequences

- Risks living in a document's silences — no kill fee, no cure period, no cap —
  have no sentence to quote. Separate treatment, or out of scope. Unresolved.
- The parser must preserve exact text and character offsets. Normalisation that
  improves readability but breaks offsets is off the table.
- Model output is validated against the source before it reaches the reader,
  and failing flags are dropped. Recall falls. That is the trade.
- Tests get a hard assertion: every returned flag's quoted sentence must appear
  verbatim in the source fixture.
- Confirms the exclusion of OCR. A citation into misread text is worse than
  none, because it still looks checkable.
