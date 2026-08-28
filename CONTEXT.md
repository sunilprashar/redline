# Redline

The language Redline uses for the people it serves and the documents they
bring it. Terms only — decisions live in `docs/adr/`.

## Language

**Signer**:
The person Redline serves: whoever is being asked to sign, reading without a
lawyer.
_Avoid_: user, customer, consumer

**Freelancer**:
The signer we tune defaults and copy for. Supplies work to clients who draft
the paperwork.
_Avoid_: contractor, gig worker, solopreneur

**Creator**:
A signer who supplies content rather than services. Inside scope, not named in
the copy — see ADR-0010.
_Avoid_: influencer

**Supplier agreement**:
Any agreement where the signer supplies work or content to the party that
drafted it. The document class Redline reads.
_Avoid_: services contract, gig contract

**Admission test**:
The three conditions deciding whether Redline will read a document: the signer
supplies the work, the other party drafted it, and a change can be accepted.
_Avoid_: eligibility, supported documents

**Brand deal**:
An agreement between a creator and a company paying them to make or feature
content. Redline's primary document.
_Avoid_: sponsorship, partnership agreement, collab

**Platform terms**:
The terms of service a creator accepts from a platform they publish on.
Out of scope for version one — see ADR-0005 — because nothing in them can be
negotiated.
_Avoid_: ToS, T&Cs, EULA

**Flag**:
A clause Redline surfaces as capable of hurting the signer, shown with the
exact sentence it came from.
_Avoid_: issue, risk, finding, alert

**Absence-flag**:
A flag raised because something protective is missing rather than present.
Carries no citation and is shown as its own kind of object.
_Avoid_: gap, missing clause warning

**Red line**:
A limit the signer sets for themselves, which changes what Redline flags and
how highly it ranks.
_Avoid_: preference, setting, rule

**Counter-offer**:
Replacement wording Redline drafts for a flagged clause, for the signer to
send back.
_Avoid_: redline (the verb), suggestion, edit

**Tier one**:
The clauses whose effects cannot be undone after signing — licence scope,
exclusivity, perpetuity, morality and conduct termination, absent payment
protection. Flagged on
suspicion rather than on confidence.
_Avoid_: critical, high severity, P0

**Clean result**:
The report for a document with nothing worth flagging, which names the tier-one
clauses searched for and not found.
_Avoid_: no issues, all clear, passed
