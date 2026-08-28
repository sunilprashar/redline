# Agent 1 — Market Research Sweep: People Hurt by Contract Terms They Didn't Understand/Notice

Scope: verbatim first-person (or near-first-person) quotes describing harm from contract terms not understood or not noticed. Reddit was excluded per known crawler blocks from prior agents.

---

## Finding 1 — Vehicle loan contract signed without understanding terms

> "I can't make 184 a month...I did not understand the contract fully...I did understand the contract"

**Who/context:** CFPB Consumer Complaint Database, Vehicle Loan complaint. Consumer disputes monthly payment obligation and claims impaired understanding of the loan contract at signing (narrative is internally contradictory in the source, noted as-is).
**Source:** CFPB Consumer Complaint Database (complaint #6572784, Feb 2023) — https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/?search_term=contract%20did%20not%20understand&field=complaint_what_happened&has_narratives=true&size=10
**Read status:** Full API/page read (tool-summarized extraction of the narrative field, not a manual re-verification against the raw JSON).
**Note:** CFPB announced Aug 14, 2026 it is ending publication of complaint narratives going forward — this data source may not be available to future agents.

---

## Finding 2 — Online payday loan contract "not explained"

> "When I sign the contract it was done on line so it was not explained to me properly and of such I did not understand it"

**Who/context:** CFPB Consumer Complaint Database, Payday Loan complaint (#2381548, Mar 2017). Consumer says the online contract-signing flow gave no real explanation of terms.
**Source:** https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/?search_term=contract%20did%20not%20understand&field=complaint_what_happened&has_narratives=true&size=10
**Read status:** Full API read (tool-summarized extraction).

---

## Finding 3 — Hidden terms in vehicle financing contract

> "Certain financial aspects of the said contracts...were hidden. I was not actually told that my signature was going to create the credit"

**Who/context:** CFPB Consumer Complaint Database, Vehicle Loan complaint (#9725097, Aug 2024). Consumer alleges the credit-creation mechanism of the contract was concealed from them.
**Source:** https://www.consumerfinance.gov/data-research/consumer-complaints/search/api/v1/?search_term=contract%20did%20not%20understand&field=complaint_what_happened&has_narratives=true&size=10
**Read status:** Full API read (tool-summarized extraction).

---

## Finding 4 — Non-compete violated without the employee realizing it applied

> "I had no idea that that would violate my NonCompete clause that i signed to when hired, being that it was not related to retail AT all, and there were no transferable skills that I learned. Luckily my lead saved my ass, and told the managers 'theres no way he knew that.'"

**Who/context:** Hacker News commenter "roflchoppa," describing signing a non-compete at a retail job and nearly being fired for an unrelated side project he didn't realize the clause covered.
**Source:** https://news.ycombinator.com/item?id=11998865 (via https://hn.algolia.com/api/v1/items/11998865)
**Read status:** Full page read — fetched the raw HN item directly and confirmed verbatim text and author.

---

## Finding 5 — Non-compete blocking the person from starting their own company

> "I signed a non-compete clause a while back and it says I can't work for any competitor startup or start my own in that niche. Apparently the non-compete extends for a year after leaving. It mentions I can't offer consulting or work for the competition. It's been a few years now, but I wonder what other dirty tricks they may have up their sleeves regarding this. I want to start my own company in this niche and I can't do it because of the fear that they will sue me if I ever make it on their radar."

**Who/context:** Hacker News commenter "cookerware," describing being unable to pursue their own business years after signing an employment non-compete.
**Source:** https://news.ycombinator.com/item?id=7568432 (via https://hn.algolia.com/api/v1/items/7568432)
**Read status:** Full page read — fetched the raw HN item directly and confirmed verbatim text and author.

---

## Finding 6 — Gym personal-training contract auto-renewed without the member's knowledge

> "I was billed for 14 months by Gold's Gym for a personal training agreement that was set to expire after only 10 months. There was no information stating that the agreement renewed itself"

**Who/context:** BBB complaint against Gold's Gym (Murfreesboro, TN location), dated 10/21/2025. Consumer says the renewal clause was silently in effect with no disclosure at signing.
**Source:** https://www.bbb.org/us/tn/murfreesboro/profile/fitness-center/golds-gym-0573-37049231/complaints
**Read status:** Full page read (tool-summarized extraction; BBB redacts some personal/business details as "REMOVED" in the source itself).

---

## Finding 7 — Gym member hit with unexpected $5,000 bill after losing their job

> "All I wanted was my account closed and REMOVED stopped as I could not afford the $400 a month"

**Who/context:** BBB complaint against Gold's Gym, dated 02/13/2026. Consumer describes trying to cancel a personal-training contract after job loss and instead being hit with an unexpected $5,000 bill (per the complaint summary).
**Source:** https://www.bbb.org/us/tn/murfreesboro/profile/fitness-center/golds-gym-0573-37049231/complaints
**Read status:** Full page read (tool-summarized extraction).

---

## Finding 8 — Gym cancellation letters allegedly never received, contract kept billing

> "I did their free personal training session and felt forced to sign up, but it was okay since their cancelation policy was to mail a certified letter to the location"

**Who/context:** BBB complaint against Gold's Gym, dated 01/20/2026. Consumer signed under pressure, relied on the stated cancellation procedure, and says the gym later claimed the certified letters were never received.
**Source:** https://www.bbb.org/us/tn/murfreesboro/profile/fitness-center/golds-gym-0573-37049231/complaints
**Read status:** Full page read (tool-summarized extraction).

---

## Finding 9 — SaaS (Adobe Creative Cloud) auto-renewal charged despite timely cancellation

> "I had a creative cloud subscription a few years ago, and fell a victim to the dreadful auto renewal feature Adobe use." / "Despite cancelling, twice in fact, and both in time (as per the contract) auto renew debited my account with an unauthorised transaction."

**Who/context:** Adobe Community forum user "michaeld24719553," Nov 22, 2018. First-person account of the ToS auto-renewal clause charging him despite following the stated cancellation process.
**Source:** https://community.adobe.com/t5/download-install-discussions/yet-another-complaint-regarding-membership-subscriptions/m-p/10138685/highlight/true
**Read status:** Full page read (tool-summarized extraction).

---

## What I could not find

- **Residential lease**, first-person, verbatim: Every attempted source (Quora, JustAnswer, Avvo, law.stackexchange, HN algolia search) either 403'd, returned zero hits, or surfaced only generic third-party advice content with no first-person narrative I could verify. I found **no sourced verbatim lease quote** and am not including one.
- **Freelance/creative agreement (IP assignment / work-for-hire), first-person, verbatim**: Freelancers Union's own testimony blog post (https://blog.freelancersunion.org/2019/06/21/why-freelancers-union-is-testifying-against-non-compete-agreements-for-freelancers/) contains named freelancer testimony (Daisy Alioto, Jess Perez), but on full-text check neither gives a first-person "I signed X and got hurt" narrative — their quotes are general policy statements, not personal harm accounts, so I excluded them as not meeting the bar. No other freelance-contract-specific verbatim quote was found within budget.
- **Small-business vendor/franchise agreement, first-person, verbatim**: Search surfaced only third-party explainer articles on personal guarantees; Avvo's specific franchise Q&A page (https://www.avvo.com/legal-answers/how-does-a-franchise-owner-protect-their-personal--2149941.html) 403'd and could not be read. No verbatim quote found.
- **FTC non-compete rulemaking docket (regulations.gov)**: Could not get a direct, individually-quotable public comment; search results only surfaced the Federal Register's own aggregate summary of commenter arguments, not verbatim submitted text with a specific commenter and URL. Not included to avoid misattributing a paraphrase as verbatim.
- Reddit was not attempted directly per prior-agent guidance; no Reddit search snippets surfaced in the queries run.

---

**Usage:** 12 web searches used (cap 12, reached). 15 page fetches used (cap 15, reached) — includes several that returned HTTP 403 (JustAnswer, Quora, Avvo) or zero hits (HN algolia lease/SaaS queries) and were still counted.
