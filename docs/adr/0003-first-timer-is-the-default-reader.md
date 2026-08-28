# 0003 — The first-timer is the default reader

Status: accepted · 2026-08-28

## Decision

Version one is built for a signer reading their first serious agreement.
Repeat signers are served by editing their red lines, not by a second mode.

## Alternatives

- **Build for the repeat signer.** Better business — recurring volume, real
  budget, and the person most able to pay. Rejected because their product
  needs a baseline of what they normally accept, and on first run there is
  none.
- **Build both, switched by a mode.** Rejected as a first version: it doubles
  the generated prose per flag, and under ADR-0001 every generated sentence is
  a place an unsupported claim can appear.

## Why

Three things fork on this choice and each ships one way. The empty state: we
ship a curated default red-lines set so the product works before it is
configured. The ranking: absolute harm, not deviation from a personal norm — a
perpetual licence tops the list for someone who has never seen one and carries
no information for someone who signs it monthly. The prose: explanatory,
because the reader does not yet know what perpetual costs them.

## Consequences

- Deviation detection — "this deal is worse than your last four" — is out.
  The saved library stores and retrieves; it does not compare.
- Repeat signers get quieter results as they tune their red lines, and never
  get told how a deal compares to their own history.
- Expect churn around the fifth deal, when the explanations become noise. The
  likely fix is a prose-density control, which is a new scope item and needs
  asking for before it is built.
