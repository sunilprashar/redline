# Redline — the brief

What version one is, who it is for, and what we decided against. Every
decision here is recorded in `docs/adr/` with its full reasoning; this brief
is the summary and the argument, not the record.

Vocabulary is defined in `CONTEXT.md` and used strictly. A **signer** is
whoever is being asked to sign. A **supplier agreement** is any document where
the signer supplies work or content to the party that drafted it.

---

## 1. Who this is for

**Freelancers and contractors signing supplier agreements they had no hand in
drafting.** Consultants, designers, developers, writers, editors, video
people. One person, no legal budget, a client who sent over a PDF and would
like it back signed.

**Creators are inside the scope and outside the copy.** A brand deal passes
the same admission test and needs the same clause taxonomy, so a creator who
uploads one gets a working product. We do not say "creators" anywhere in the
marketing, because someone with a YouTube channel and a $4,000 brand deal does
not search for freelance contract review and does not call themselves a
freelancer. Reaching them is a second landing page, not a second product.
(ADR-0010)

### What they do today instead

Four substitutes, in rough order of how often they are used:

1. **Sign it.** The default. No reading, or reading without knowing what to
   look for.
2. **Paste it into ChatGPT.** Free, immediate, and the honest competitor. A
   seller of freelance contract templates describes the whole journey in one
   line: after struggling with contract rewriting they "learned that I might
   as well have just used ChatGPT," and went on to build a product teaching
   freelancers to let "ChatGPT do the heavy work for you" instead of paying a
   lawyer. — https://ajelmar.gumroad.com/l/legal-ai (`agent-4.md`)
3. **Buy a cheap human review.** Fiverr contract-review gigs run **$20–57**,
   up to $150–500 for senior freelancers, with pitches like *"Lawyers are
   costly, Let me offer a less expensive option."* This is the only revealed
   purchasing behaviour anywhere in our research — freelancers already buy this
   category, at this price. — https://www.fiverr.com/gigs/contract-review
   (`agent-4.md`)
4. **Hire a lawyer.** ContractsCounsel marketplace averages: consulting
   contract review **$500**, business contract review **$470**, employment
   contract review **$608**. — https://www.contractscounsel.com/b/contract-review-cost

**We are priced against $0–57, not $608.** Every four-figure number in the
research folder is what a different customer pays. This single fact should
govern pricing, scope, and how much the product is allowed to cost to run.

---

## 2. The problem

A supplier agreement is written by the party with the lawyer, read once by the
party without one, and binding on both. The signer cannot tell which sentences
are ordinary and which are unusual, because they have no basis for comparison.

**The failure mode, in a signer's own words.** Our strongest verified
first-person account is from outside this segment — a retail employee who
signed a non-compete and nearly lost his job over an unrelated side project:

> "I had no idea that that would violate my NonCompete clause that i signed to
> when hired, being that it was not related to retail AT all, and there were no
> transferable skills that I learned. Luckily my lead saved my ass, and told
> the managers 'theres no way he knew that.'"

— Hacker News, verified verbatim against the raw item.
https://news.ycombinator.com/item?id=11998865 (`agent-1.md`, Finding 4)

The clause was read. It was signed. It was not understood to cover the
conduct. That is the exact failure Redline addresses, and note what would have
helped: not a summary, but a sentence saying *this covers side work in any
industry.*

**The scale, for our segment.** A joint survey by Freelancers Union, the
Authors Guild, the Graphic Artists Guild and others found **62% of New York
freelancers had lost wages at least once** to nonpayment, and **under 1% ever
pursued legal action.**
https://authorsguild.org/news/survey-finds-62-percent-of-ny-freelance-workers-have-lost-wages-due-to-nonpayment/
(`agent-2.md`)

That second number is the harder one. People who have already been harmed,
with a clear claim, overwhelmingly do nothing. We are asking for attention
*before* harm, when urgency is at its lowest.

**Where the nonpayment harm is actually addressable.** Our own research agent
records that this is not a bad-clause problem but a missing-clause one — it is
"about the *absence* of payment-protection language (late fees, kill fees,
escrow, milestone terms)" — and names a drafted counter-offer as "exactly the
kind of intervention this survey population needs" (`agent-2.md:125`). Adding
a kill fee before signature is a pre-signature fix. Chasing an invoice after
the fact is not, and we cannot help with it.

**What nothing in the research supports.** There is no first-person account
anywhere in the folder of a freelancer harmed by a contract term they did not
understand. `agent-1.md` looked, found named freelancer testimony at
Freelancers Union, and excluded it for being policy argument rather than
personal harm. Section 8 sets out why we do not read that as evidence of
absence — but we should not pretend it is evidence of presence either.

---

## 3. What the first version does

Exactly these nine things.

1. **Accepts a document that passes the admission test** — the signer supplies
   the work, the other party drafted it, and a human on the other side can
   accept a change.
2. **Parses the file in the browser.** Only text leaves the device.
3. **Produces a plain-English summary** of what the document commits the
   signer to.
4. **Flags clauses that could hurt the signer**, ranked by severity, using the
   tier list in section 5.
5. **Shows the exact source sentence for every flag**, quoted verbatim. A
   flag whose sentence cannot be shown is not displayed.
6. **Drafts a counter-offer for each flagged clause** — replacement wording
   the signer can send back.
7. **Answers questions about the document, from the document only.**
8. **Lets the signer edit their own red lines**, which changes what is flagged
   and how it ranks.
9. **Saves a document to a library, when the signer opts in per document.**

**Nothing else.** When something looks like the obvious next step and is not
on this list, ask before building it.

---

## 4. What good looks like

Version one exists to prove the analysis can be trusted. Everything below is
measured against a corpus of **at least 15 real supplier agreements** the team
did not write — executed contracts filed as exhibits on SEC EDGAR are the
cheapest honest source — with tier-one clauses hand-labelled before the
pipeline runs.

These are the numbers that decide whether this works. They are stated as
thresholds so they can fail.

| # | Measure | Threshold | What failing it means |
|---|---|---|---|
| 1 | **Citation survival** — of all flags the model generates, the share whose quoted sentence appears verbatim in the source | **≥ 80%** | Below this, the model cannot reliably quote and ADR-0001 is silently discarding most of the analysis |
| 2 | **Displayed citation accuracy** — of flags actually shown, the share whose sentence is verbatim | **100%** | Anything under 100% is a bug, not a metric. One fabricated citation destroys the premise |
| 3 | **Tier-one recall** — hand-labelled tier-one clauses that get flagged | **≥ 90%** | A missed perpetual licence is the failure that hurts someone. This is the number that matters most |
| 4 | **Flags per document** — median, on an 8-page agreement | **≤ 8** | Above this the report is unreadable and the tier-one flags are buried, regardless of accuracy |
| 5 | **Tier-one precision** | **≥ 50%** | Deliberately loose, per ADR-0006. Below half, the product reads as panicking |
| 6 | **Clean-result behaviour** — documents with no tier-one clause that correctly return a clean result | **100%** | A product that manufactures a finding on a fine document stops being read |
| 7 | **Counter-offer soundness** — drafted clauses that change the flagged term without introducing a new obligation on the signer | **≥ 90%**, judged by hand | A counter-offer that quietly makes things worse is worse than none |

**The thresholds are set by judgment, not derived from anything.** No source
in the research folder says what citation survival rate is acceptable. They
are set at levels that would force a real decision if missed, and the first
corpus run should be treated as calibrating them as much as passing them.

Measures 1, 3 and 4 are the ones most likely to fail, and each would force a
specific decision to be reopened: 1 → ADR-0001, 3 → ADR-0004, 4 → ADR-0006.

**What we are explicitly not measuring in version one:** whether anyone will
pay, whether anyone will return, and whether the counter-offers get accepted
by the other side. Those matter more commercially and cannot be tested without
users we do not have.

---

## 5. My red lines

Severity is **magnitude as the document states it** — the length of a term,
the breadth of a grant, the size of a stated penalty — with **irreversibility
breaking ties**. We do not estimate what a clause will cost, because that
number is not in the document and inventing it would break the rule that we
state only what the text says. (ADR-0004)

### Tier one — flagged on suspicion

Generous here. A false positive costs the signer two minutes; a false negative
costs them something they cannot get back. (ADR-0006)

| Clause | Why it is tier one |
|---|---|
| **IP assignment and licence scope** | The signer's inventory. A grant that is worldwide, sublicensable, or covers work beyond this engagement transfers the thing they sell. The Authors Guild finds 67% of writers do not know what rights their contract grants |
| **Exclusivity** | Removes future income that is invisible at signing. A category exclusivity means every competitor is closed to them for the term, and they will not notice until they are turning work down |
| **Perpetuity** | No end date means no recovery. Every other term expires; this one does not |
| **Morality and conduct termination** | Termination at the client's sole discretion, judged subjectively. The signer cannot comply with a standard they cannot read |
| **Absent payment protection** | No kill fee, no milestones, no late-payment term. The best-documented harm in this segment, and the only tier-one entry with no sentence to quote — it is presented as an absence-flag under ADR-0011 and ships after the cited flags |

### Tier two — flagged on confidence

| Clause | Why it matters |
|---|---|
| **Unilateral amendment** | Silently voids everything around it. Whatever else the document says, it says it only until the other party changes it |
| **Auto-renewal** | The best-evidenced harm in the whole research folder — ~70 FTC complaints a day in 2024, up from 42 in 2021 — though it belongs to consumers more than to freelancers |
| **Arbitration and class-action waiver** | Removes a remedy the signer does not know they have. Ranks below tier one because it changes the forum, not the substance |

### Tier three — flagged on confidence, ranked low

Payment terms, deliverables and revision limits, approval rights.

**What is deliberately not on this list.** Limitation of liability and
indemnification. Both were in the original hypothesis; two independent
research passes found essentially no complaint evidence for them among people
like our signers. They are negotiated hard by sophisticated commercial
parties — a different customer.

**This ranking is our judgment, not the research's.** The research's ranking
was built across gym members, borrowers and retail employees, and exclusivity
does not appear in it at all — it was dropped for search budget, not found
unimportant. Nothing in the folder validates the order above.

---

## 6. The calls I made, and what I gave up

**Every flag cites its exact source sentence; one that cannot be shown is not
shown.** (ADR-0001) *Chose against:* letting the model describe risks in its
own words, which is fluent, tolerant of messy input, and the shape of every
free chatbot answer. *Worse off:* the signer whose real risk was found but
whose citation failed verification — they see nothing at all, and recall falls
to buy verifiability.

**Freelancers are the segment; scope is the admission test.** (ADR-0010)
*Chose against:* creators, who were the original choice and were reversed. The
research holds two creator lines, both lawyers' price lists, and no
first-person harm account. *Worse off:* creators, who get a product that works
for them and never says their name; and us, since the segment we can reach is
also the one whose market clears at $20–57.

**The first-timer is the default reader.** (ADR-0003) *Chose against:* the
repeat signer, who has budget, volume, and recurring need. *Worse off:* the
person most able to pay us. They get explanatory prose they no longer need,
and no way to see how this deal compares to their last ten. Expect churn
around the fifth document.

**Severity is stated magnitude, not estimated harm.** (ADR-0004) *Chose
against:* ranking by what a clause will actually cost, which is what a signer
would most like to know. *Worse off:* anyone whose worst clause is one whose
danger is real but unstated in the text.

**Generous in tier one, strict below it.** (ADR-0006) *Chose against:* uniform
tuning. *Worse off:* the experienced signer, who will see standard licence
grants flagged and conclude the product panics — and the signer whose problem
is scope creep, which sits in tier three and is tuned quiet.

**Confident about the text, silent about the law.** (ADR-0007) *Chose
against:* answering the questions signers most want answered — is this legal,
would this hold up. *Worse off:* every user, on the two questions they came
with. The alternative is the claim the FTC sanctioned DoNotPay for.

**A clean result names what it looked for and did not find.** (ADR-0008)
*Chose against:* "no significant risks found," which is honest and
unbelievable. *Worse off:* nobody directly — but this is the one screen where
ADR-0001 does not reach, because an absence has no sentence to quote.

**Retention is opt-in and the model route is published.** (ADR-0009) *Chose
against:* a library that works by default and improves with every document.
*Worse off:* the repeat user again, who now pays a decision per document for
the history that would have made document ten better than document one.

**Absence-flags are a distinct object, and ship second.** (ADR-0011) *Chose
against:* showing them identically to cited flags, which is simpler and
quietly weakens the guarantee everything else rests on. *Worse off:* the
freelancer whose central harm is missing payment protection — the thing we
named the segment for arrives in the second release, and the copy must not
claim it before then.

---

## 7. What we are not building

**Excluded on principle, not backlogged.**

- **Payments and billing.** Version one exists to prove the analysis can be
  trusted. Neither makes it more trustworthy.
- **OCR for scanned documents.** This one actively undermines the product: a
  citation into misread text is worse than no citation, because it still looks
  checkable. (ADR-0001)
- **Sharing a document between users.**

**Excluded because they break something we decided.**

- **Platform terms of service.** Nothing in them can be negotiated, so the
  counter-offer — one of nine features — is dead on arrival. A creator's
  platform terms can end their income overnight and we are choosing not to
  look. (ADR-0005)
- **Employment contracts, residential leases, franchise disclosure
  documents.** Each fails the boundary rule: admitting them would require
  adding clause types to tier one, which is an edit to ADR-0004 rather than a
  scoping call. Leases additionally face eight existing competitors.
- **Legal conclusions of any kind.** (ADR-0007)

**Excluded for now, with the trigger named.**

- **Deviation detection** — "this deal is worse than your last four." Requires
  comparing across the library; the library stores and retrieves. Revisit when
  a signer has enough saved documents for a comparison to mean anything.
- **A prose-density control** for readers who no longer need the explanations.
  The likely fix for fifth-document churn. Needs asking for before building.

---

## 8. What the research could not tell us

Read this section before treating anything above as validated.

**Nobody will confirm they would pay.** Two passes, different briefs, same
null: no verbatim "I'd pay $X," no "$X is too expensive" attached to a number,
no conversion or elasticity data from any comparable product. Every price we
have is what someone was *charged* by a lawyer, or a vendor's list price with
no demand behind it. **The commercial premise of this product is
unevidenced.** The one exception is the Fiverr $20–57 band, which is revealed
behaviour rather than a stated preference, and which sets a ceiling as much as
it proves a market.

**That null is less thoroughly established than it looks.** `agent-4.md` used
**6 of its 15** page fetches before stopping, and `agent-3.md` also used 6.
`agent-1.md` exhausted its budget at 15/15, so its nulls are well-tested and
theirs are not. The willingness-to-pay null is probably right; it is not as
firmly established as the folder's summary presents it.

**No first-person freelance harm account exists in the folder.** Not because
freelancers are unharmed — because Reddit hard-blocked every agent (400/403,
and `site:reddit.com` filters silently stripped by the search backend), and
that is where these conversations happen. Quora, Avvo, G2 and JustAnswer
returned 403 throughout. **The lease and freelance evidence gaps are crawler
artifacts, not findings.** Closing them means reading manually, not running
another agent.

**One cited source contradicts a claim built on it.** The Clio figures on
affordability appetite were relayed from a search-engine snippet after the
primary page returned 403 — and Clio's own analysis puts cost's measured
impact on the decision to avoid a lawyer at **0–5%**. Cost complaints exist;
they are not shown to drive behaviour.

**Sources are closing.** CFPB stopped publishing complaint narratives in
August 2026, which retires the source behind three of `agent-1.md`'s nine
findings.

**The nearest competitors are unreviewed.** Eight consumer lease-review
products, zero independent review coverage on any of them. Consistent with a
market where products ship and never find users.

**Our differentiator is real and cheap to copy.** The two named complaints
about using ChatGPT for contract review are confidentiality and lack of
source-grounding, and our design answers both. But the third named complaint —
no interpretive skill on ambiguous or unconventional language — we do not
answer, and that one is about analysis quality rather than output format.

**What would actually resolve the open questions.** Distribution first: we can
reach neither segment today, which is the real blocker and is not a research
problem. Then the corpus in section 4, which can prove several decisions above
wrong for the price of a weekend. More desk research on the segment question
would produce nothing; that folder has been read to exhaustion.
