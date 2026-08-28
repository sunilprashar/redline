# Redline

A web app for people signing a contract, lease, freelance agreement, or terms
of service without a lawyer. It tells them what they are actually agreeing to.

## Scope

Build exactly these, then stop:

- Plain-English summary of the document
- Clauses that could hurt the reader, ranked by severity
- The exact source sentence shown for every flagged clause
- A drafted counter-offer for each flagged clause
- A question box that answers only from the document
- An editable list of the user's own red lines, which drives the analysis
- A saved library of past documents

When something looks like the obvious next step and is not on that list, ask
before building it.

## Deliberately excluded

Payments, billing, OCR for scanned documents, and sharing a document between
users. These are not backlog items or oversights.

This version exists to prove the analysis can be trusted. None of those make it
more trustworthy, and OCR actively undermines it: a citation is worthless when
the text it points at was misread.

## Settled decisions

Not open for reinterpretation. If one looks wrong, raise it rather than route
around it.

- Next.js, Supabase for auth and database, deployed on Vercel
- The uploaded file is parsed in the browser; only text is stored
- Every risk flag cites the exact sentence it came from — a flag whose source
  cannot be shown is a bug, not a degraded result
- The product calls its model through OpenRouter

## Standing rules

- Keep credentials in `.env.local`, which is gitignored. Never commit a secret:
  a key is public the moment it is pushed and has to be rotated.
- State only what the document says. Where the text does not support a claim,
  the product does not make it.
- Ask before adding a dependency.

## Read before you start

- `research/summary.md` — the user research. Read it before deciding what the
  product should do.
- `PRD.md` — the brief, once it exists. Read it before building.

## Agent skills

### Issue tracker

Issues live as GitHub issues in `sunilprashar/redline`, managed with the `gh`
CLI. See `docs/agents/issue-tracker.md`.

### Domain docs

Single-context: `CONTEXT.md` and `docs/adr/` at the repo root. See
`docs/agents/domain.md`.
