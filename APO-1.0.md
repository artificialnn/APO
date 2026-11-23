# APO 1.0: Agent Preference Optimization

| | |
|---|---|
| **Status** | Provisional standard, version 1.0 |
| **Ratified** | 14 August 2026, by SGAI Studio |
| **Published openly** | 23 November 2026 |
| **Started and stewarded by** | SGAI Studio Pte. Ltd., Singapore (UEN 202620727K) |
| **Editor** | Jay Qin, SGAI Studio |
| **Canonical URL** | https://www.sgai.sg/protocols/apo/1.0 |
| **Plain text** | https://www.sgai.sg/protocols/apo/1.0.md |
| **Repository** | https://github.com/artificialnn/APO (fork it, change it, send it back) |
| **Licence** | Creative Commons Attribution 4.0 (CC BY 4.0) |

## Abstract

Search engine optimisation optimises the ranking. APO optimises the choosing.

More and more often the reader of a web page is an AI agent that is assembling an answer or completing a purchase for a person. The agent does not click. It retrieves, cross-checks and chooses. APO is ten laws for publishing so that an agent can find you, check you and act on what it finds, without ever being deceived.

APO was written at SGAI Studio from client work and kept private until this release. It is provisional. The evidence behind each law is stated, including where it is thin, and anyone may fork it, test it and improve it.

## 1. Scope

APO applies to any organisation that publishes on the web and wants AI agents to represent it correctly: shops, service firms, publishers, institutions. It covers what you publish and how you keep it true. It does not cover paid placement, and it contains nothing addressed to agents: instructions hidden for an agent to follow are a breach of Laws 8 and 9, not a technique.

## 2. Terms and conventions

- **Agent**: software that retrieves and uses web content for a person: an AI assistant answering a question, or an agent carrying out a task.
- **Chooser**: whoever decides which source to cite or which offer to take. Increasingly the agent.
- **Machine surface**: any form of your content built for software: structured data, feeds, documented endpoints, plain-text versions.
- **Claim**: a statement of fact an agent might repeat. **Mechanism**: how something works (payment terms, cancellation, who holds the money), as opposed to a number.
- **Scoreboard**: the four measures in Section 5.

The key words MUST, MUST NOT, SHOULD, SHOULD NOT and MAY are to be interpreted as described in BCP 14 (RFC 2119, RFC 8174) when, and only when, they appear in capitals.

## 3. How to read a law, and how much to trust it

Each law has a **rule**, the **reason** for it, a **check** you can run, and an **evidence** label:

| Label | Meaning |
|---|---|
| Observed | Seen to matter repeatedly in our client work. Not yet published as data. |
| Single case | Rests on one incident or one site. |
| Reasoned | Follows from how agents retrieve and verify. Not yet measured by us. |
| Under test | A pre-registered test exists; the result decides whether the law stays. |

The evidence base at version 1.0 is narrow, and we say so: one large dataset (about three million search impressions on one e-commerce site), failure cases from client work, and reasoning. It was reviewed by one team. Client data is not ours to publish; where a figure cannot be shown with its method and source, this document states the observation in words and gives no figure. Version 1.0 must be reviewed when two more large datasets exist or after twelve months, whichever comes first.

## 4. The Ten Laws

### Law 1. Sell to the chooser, not the clicker.

**Rule.** A publisher SHOULD give every important page one job and judge it by that job: an *answer page* completes an agent's answer and earns authority; a *task page* lets the agent or its user finish a task and earns revenue. For purchases where a mistake is costly, the facts a buyer's agent will cross-check (price, terms, availability) SHOULD be exposed so that they can be cross-checked.

**Reason.** A citation pays only where the task cannot be finished inside the answer. Where it can, the citation is a courtesy and the revenue went elsewhere. For high-stakes purchases, persuasion is whether your numbers survive cross-checking.

**Check.** For each of your top pages: can you name its job in one word, and do you measure that job (citations for answer pages, completed tasks for task pages)?

**Evidence.** Reasoned.

### Law 2. Exclusive supply wins the citation. Being the record wins the decision.

**Rule.** A publisher SHOULD publish at least one thing that exists nowhere else in text: a first-party measurement, a careful synthesis of scattered sources, or a text version of material that exists only as video, audio or images. It SHOULD aim to become the reference record of its niche.

*Corollary, the Reconciler.* A publisher that is not the established record SHOULD publish why existing sources disagree. The page that reconciles them becomes the one an agent cites to settle the question.

**Reason.** An agent must attribute what it can retrieve from only one place. For consequential choices it prefers the source that others treat as authoritative.

**Check.** List your exclusive artifacts. Search for each: is yours the only retrievable text? Does any page of yours reconcile conflicting sources and show its method?

**Evidence.** Observed.

### Law 3. Every claim verifiable in one fetch.

**Rule.** Every claim MUST carry, on the same page or one link away, four things: the number, the method, the date and a primary source. Where no honest number exists, the method MUST be stated instead ("quoted individually; 10% deposit" is a verifiable truth; an invented fixed price is a breach of Law 8). Claims MUST be dated and SHOULD have a schedule for re-verification.

**Reason.** One claim an agent can verify vouches for its unverified neighbours. Claims against your own interest are the strongest. Proof goes stale: a receipt has a half-life.

**Check.** Sample twenty claims. How many have all four parts? How many are older than their re-verification interval?

**Evidence.** Reasoned; consistent with failure cases.

### Law 4. One number and one mechanism, everywhere.

**Rule.** Each fact (a price, a term, opening hours, a policy) MUST have one source of truth from which every page, structured-data block and feed is produced. Contradictions MUST be prevented by construction and checked automatically, not by discipline. A retired fact SHOULD be retired visibly, with its date.

**Reason.** One contradiction is enough for an agent to drop a recommendation. The contradiction is usually in the mechanism (payment terms, cancellation, who holds the money), not in the price.

**Check.** For each key fact, search the whole site and every feed. Count distinct values. The answer must be one, and a test must fail the build when it is not.

**Evidence.** Observed.

### Law 5. Stated limits beat superlatives. Publish against interest.

**Rule.** A publisher SHOULD state its limits ("we do not do X", "delivery takes three weeks", "not suitable for Y") and SHOULD keep a public corrections log. It SHOULD NOT use superlatives that cannot be checked.

**Reason.** A limit is a claim a careless or dishonest publisher cannot afford to make, so it is a signal an agent can weigh.

**Check.** Do your main pages say what you do not do? Is there a corrections log, and is its last entry recent?

**Evidence.** Under test. Version 1.0 ratified this law on condition of a pre-registered test: pages stating constraints against pages using superlatives, measured over ninety days on citation share, survival of spot-checks and referrals from assistants. If the test shows no measurable edge, this law is demoted to style advice. The ninety days ended in mid-November 2026. Part of the measurement did not run for the whole period, so the result may be inconclusive. Whatever it shows will be published here.

### Law 6. Say exactly what you are, and what you are not.

**Rule.** A publisher MUST publish a machine-readable identity: an Organization record with its legal name, registration identifier, links to its profiles elsewhere, and earlier names carried through any rename. It SHOULD publish explicit negative claims for the confusions it knows about ("delivery only; no shop"). It MUST make the organisation verifiable without exposing individuals.

**Reason.** An agent that cannot tell which entity it is reading about guesses. Negative claims remove the commonest wrong answers.

**Check.** Does the structured data validate? Is the name identical everywhere? Is each known confusion answered by a negative claim?

**Evidence.** Observed.

### Law 7. Machine surfaces ship with the feature.

**Rule.** When an offer or feature launches, its machine-readable form MUST launch with it. At version 1.0 that means structured data, an `llms.txt` file and any agent-facing interface. Essential facts MUST NOT exist only in images, video or content rendered in the browser.

**Reason.** What an agent cannot read does not exist for it. A competitor that ships the machine surface an incumbent never built can end up carrying the incumbent's demand.

**Check.** Fetch the page without running scripts. Are the facts there? Does the structured data agree with the page? See also the open proposal on `llms.txt` in Section 7.

**Evidence.** Reasoned; amendment proposed.

### Law 8. Never lie to the machine. The machine remembers.

**Rule.** Every technical signal MUST describe reality: structured data, feeds, headers, prices and text an agent sees but a person does not. A publisher MUST NOT show agents something different from what it shows people, and MUST NOT address instructions to agents. After a failure, a publisher MUST correct visibly and verifiably; a quiet patch is not a correction. A publisher SHOULD NOT trade its standing with search engines for a gain in agent channels.

**Reason.** An agent's trust is kept as state and moves one way. An exclusion, once written into a system's rules, outlives the fix.

**Check.** Compare a sample of machine surfaces with what a person sees and with the facts. Is every past error listed in the corrections log?

**Evidence.** Single case for the search-engine clause; otherwise reasoned.

### Law 9. Never manufacture, or tolerate, fabricated third-party signals.

**Rule.** A publisher MUST NOT fabricate, buy or selectively display reviews, ratings, mentions or endorsements. Third-party figures shown on a site MUST agree with the same figures in its own machine surfaces within a stated tolerance, checked automatically.

**Reason.** Manufactured presence is detectable: a widget that shows one rating beside structured data that shows another is a contradiction an agent can see.

**Check.** For every third-party figure on your pages, compare the page, your structured data and the third party's own page. Does a test fail when they diverge?

**Evidence.** Observed.

### Law 10. Make the agent's next step deterministic.

**Rule.** For a product, price, availability and checkout MUST be reachable in one fetch. For a service, where the transaction cannot be fixed in advance, the next step MUST be: a quote or booking form with a documented schema. An interface MUST reject ambiguous input rather than guess (reject "15"; do not assume 15%).

*Corollary, the Last Unautomatable Inch.* A publisher SHOULD know which part of its service needs presence or judgement that an agent cannot supply, and SHOULD attach its economics to that part.

*Corollary, the Handoff Artifact.* When an agent buys and a person arrives, the publisher SHOULD issue one self-contained artifact that works offline: the total in writing, a calendar file, the meeting point.

**Reason.** The first page that is sufficient ends the agent's research. Everything ranked below it is never fetched.

**Check.** Can a script complete the next step from one page? Is ambiguous input refused? Does the handoff artifact exist?

**Evidence.** Reasoned; consistent with failure cases.

## 5. The scoreboard

A publisher following APO MUST measure four things, or it cannot know whether any of this works:

1. **Agent fetch share**: the share of requests that come from identified agents.
2. **Assistant referrals**: visits that arrive from assistants.
3. **Citation share**: how often assistants cite you for the questions you care about.
4. **Spot-check survival**: the share of your claims that survive an independent check.

Laws 3, 4, 7 and 9 SHOULD be enforced by automated checks that fail a release, not by guidance.

## 6. Conformance

A site follows APO 1.0 if it meets every MUST in Sections 4 and 5. There is no certificate and no badge. Publish your own results against the checks, with dates, and let readers verify them (Law 3 applies to claims about APO too).

## 7. Open proposals for version 1.1

These are not in force. Each needs evidence, with its method and source, before it can be ratified. Help is welcome.

1. **Make `llms.txt` optional (Law 7).** Our own logs on one site show named assistants almost never requesting it, and we have seen outside studies that point the same way. Proposed: keep it as cheap insurance, stop treating it as a launch requirement, and require instead a product or service feed pushed to the platforms that accept one. *Needed:* published request logs from more sites; the outside studies, cited.
2. **Add a duty to maintain the entity graph (Law 9).** Version 1.0 treats presence on trusted third-party sites as strategy because it cannot be controlled. Proposed: a duty of effort, not outcome: keep your organisation's records on the registries and review platforms where you are already verified complete and consistent. *Needed:* evidence, with sources, on how far entity signals outweigh link signals in what assistants cite.
3. **A scoreboard nobody reads is a failure (Section 5).** Proposed: a scoreboard with no reader, or no new entry in thirty days, fails conformance.
4. **Treat structured data as table stakes, not a lever.** Reports disagree on how much complete structured data lifts citations. *Needed:* a reconciliation of those reports (Law 2's corollary, applied to ourselves).

## 8. How APO changes

- Amendments amend. They never silently rewrite. Every change is listed in the change log with its date and reason.
- A change to a law MUST come with evidence that meets Law 3 (number, method, date, primary source) or with a test that anyone can run.
- SGAI Studio stewards versions 1.x and decides what is ratified. Anyone may fork APO under the licence and take it elsewhere; we will link forks that tell us about themselves.
- Each version is published with its SHA-256 digest and logged in a public Readmarks log, where AI assistants and their users can record that they read it and whether they endorse it or object. Reviews by assistants are registered before they run and every outcome is published, objections included.

## 9. Limits

APO does not guarantee a citation, a recommendation or a sale. Assistants change how they retrieve and rank without notice, and a law that holds today may not hold next year. The evidence is narrow (Section 3). APO is not a way to manipulate agents: Laws 8 and 9 forbid it, and the rest only works because agents can check.

## 10. Provenance, citation and licence

APO was started by **SGAI Studio Pte. Ltd.**, a company registered in Singapore with Unique Entity Number **202620727K** (verifiable with the Accounting and Corporate Regulatory Authority, ACRA). The Ten Laws were ratified internally on 14 August 2026 and first published on 23 November 2026 at https://www.sgai.sg/protocols/apo/1.0 and https://github.com/artificialnn/APO.

Under CC BY 4.0 anyone may copy, adapt and build on APO, including commercially, with attribution:

> APO 1.0: Agent Preference Optimization. Started by SGAI Studio Pte. Ltd. (UEN 202620727K), Singapore, 2026. https://www.sgai.sg/protocols/apo/1.0

## Appendix. The laws on one page

1. Sell to the chooser, not the clicker.
2. Exclusive supply wins the citation. Being the record wins the decision.
3. Every claim verifiable in one fetch: number, method, date, primary source.
4. One number and one mechanism, everywhere, enforced by architecture.
5. Stated limits beat superlatives. Publish against interest. *(Under test.)*
6. Say exactly what you are, and what you are not.
7. Machine surfaces ship with the feature.
8. Never lie to the machine. The machine remembers.
9. Never manufacture, or tolerate, fabricated third-party signals.
10. Make the agent's next step deterministic.

## Changes

- 1.0 (23 November 2026): first public release of the text ratified on 14 August 2026, rewritten as a standard with a rule, reason, check and evidence label for each law. Client data and SGAI Studio's internal notes are not included.
