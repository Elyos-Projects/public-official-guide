# Public-Official-Guide — PLAN.md

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

A non-partisan, open-source AI guide that helps public and elected officials — especially small,
under-resourced local offices with no staff — understand and fulfill their statutory duties, serve
constituents well, and govern ethically and transparently. It adapts the proven architecture of the
Ofelia app (a private long-horizon memory layer + specialized AI modules + calibrated predictions +
outcome tracking + a daily briefing) but **deliberately inverts its purpose**: from optimizing one
person's *advantage* to serving the office-holder's *fiduciary duty to constituents and the public
interest*.

---

## Executive summary

Local government runs on people who often hold office part-time, with little or no staff, no legal
counsel on call, and a thicket of statutory duties, ethics rules, open-meeting and public-records
laws they are nonetheless bound to follow. Mistakes are common, consequential, and erode public
trust. Public-Official-Guide gives those officials a private, source-cited assistant that explains
*what the office actually requires*, helps them serve constituents, and flags when a contemplated
action may cross an ethics, transparency, or conflict-of-interest line — always as **information,
not legal advice**, and always grounded in the primary law of the official's jurisdiction.

The single most important design fact is the inversion. Ofelia is built to maximize one person's
leverage and dominance; a tool that did that for an elected official would be actively harmful to
democracy. This project is built on the opposite premise and is **engineered to refuse misuse**. The
**guardrail / public-duty policy layer is the first build item and a hard product requirement** —
adversarially tested, not a disclaimer footer. It is non-partisan; it refuses campaign work,
electioneering, fundraising, opposition research, and re-election optimization; it refuses to help
evade transparency, open-records, or ethics law; it forbids constituent surveillance, profiling,
manipulation, and political targeting; and it optimizes for lawful duty and constituent outcomes
over optics and spin. Every later faculty is mounted behind this layer and cannot be reached around
it.

This is a **HIGH risk-tier** project on its legal/ethics/governance surface. No duty- or
compliance-related content ships without review and sign-off by a **credentialed expert** (a
government-ethics professional and/or a licensed attorney for the relevant jurisdiction), and
jurisdiction-specific claims must be sourced to primary law (statute, charter, ordinance, or
official ethics-board guidance). Misuse — not inaccuracy — is the top risk, and the guardrail layer
is treated and tested as a safety-critical subsystem.

Honesty note: **no pilot office or requestor is yet secured.** Every delivery-dependent task is
marked `TO BE SECURED` with `verifiedNeed: false` until a real official adopts the tool. The
project is not "shipped" on merge; it is shipped only when a real office uses it to fulfill a duty
or improve a constituent outcome, with the guardrails independently verified.

---

## Problem & beneficiaries

**Who is helped (directly):** elected and appointed public officials in small or under-resourced
offices — town/city councilmembers, county commissioners, school-board members, special-district
boards, mayors of small municipalities, planning/zoning board members, clerks — who carry full
fiduciary and legal duties without the staff, counsel, or onboarding that larger governments enjoy.

**Who is helped (ultimately):** their **constituents and the public**, who benefit from
better-informed, more ethical, more responsive, and more transparent local governance.

**The need.** New officials routinely take office with no structured explanation of their statutory
duties, oath, powers, and the ethics/transparency rules that bind them. Open-meeting and
public-records violations, undisclosed conflicts of interest, improper use of official resources,
and records-retention failures are frequent — usually from ignorance, not malice — and they harm
constituents and trust. Authoritative information exists (state statutes, municipal charters, ethics
commission guidance, clerk associations, leagues of cities) but is fragmented, jargon-heavy, and
hard to apply to a concrete situation at the moment of decision.

**Verified need / partner:** **TO BE SECURED.** No specific pilot office, official, or sponsoring
civic organization has yet agreed to adopt or co-develop the tool. Target partner profiles to
pursue: a small municipality or special district; a state municipal league, association of
counties, or clerks' association; a nonpartisan good-government NGO (e.g., a state-level
ethics/transparency organization); or a university public-administration / government-ethics
program willing to provide credentialed review. Until one is secured, the project builds the
agent-neutral platform, the guardrail layer, and one *illustrative* jurisdiction's content for
review, and marks all delivery/adoption work `TO BE SECURED`.

---

## Goals and non-goals

**Goals**

- Build an open-source, non-partisan platform that helps officials understand and fulfill their
  statutory duties and serve constituents lawfully and well.
- Ship a guardrail / public-duty policy layer that *provably* refuses partisan, campaign,
  surveillance, and transparency-evasion misuse, verified by adversarial testing and an independent
  reviewer.
- Represent one pilot jurisdiction's office duties, ethics rules, and transparency obligations as
  structured, primary-source-cited content reviewed by a credentialed expert.
- Provide privacy-first constituent casework that improves service outcomes and never enables
  political use of constituent data.
- Generate balanced, cited meeting/vote briefings that *inform* an official's judgment without
  substituting for it.
- Track real constituent-impact outcomes, and prove (via an eval) that memory-grounded, cited
  guidance beats blank-slate LLM output on accuracy and groundedness.

**Non-goals**

- Not a campaign, election, fundraising, or political-strategy tool — for any party or candidate.
- Not legal advice and not a substitute for counsel, the clerk, or the ethics board.
- Not an autonomous actor: it never files, votes, sends constituent communications, or takes
  official actions on a user's behalf.
- Not a constituent surveillance, profiling, sentiment-targeting, or voter-data system.
- Not a public scorecard, "performance" ranking, or PR/optics optimizer for officials.
- Not a 50-state legal database at launch — depth and verified accuracy for one jurisdiction first,
  breadth later, and never breadth without expert review.

---

## Success metrics (outcomes)

Outcome-centric, beneficiary-first. Vanity metrics (DAU, sessions) are explicitly **not** success.

| Metric | Baseline | Target (pilot) | How measured |
|---|---|---|---|
| Guardrail refusal rate on the misuse red-team suite | none | 100% of suite refused/redirected; 0 known bypasses | Automated adversarial eval in CI + independent reviewer audit |
| Duty/compliance claims sourced to primary law | n/a | 100% of shipped claims carry a primary-source citation | Expert review checklist; citation-coverage test |
| Expert sign-off before duty/compliance content ships | n/a | 100% of HIGH-tier content has recorded credentialed sign-off | Governance log |
| Memory-grounded vs. blank-slate quality delta (eval) | n/a | grounded clearly beats blank-slate on accuracy + citation | LLM-judge eval harness (groundedness, accuracy, fit) |
| Constituent cases moved to resolution by a pilot official | 0 | ≥ 10 cases tracked to a recorded outcome in pilot | In-app outcome tracking (with official's confirmation) |
| Documented duty/compliance improvements attributable to use | 0 | ≥ 3 concrete instances (e.g., a flagged COI disclosed, a records-retention gap fixed) | Pilot official's attested log |
| Constituent PII footprint | n/a | minimized + encrypted at rest; retention/deletion enforced | Privacy review + data-retention tests |

The **defining success outcome** (Definition of Shipped): a real official/office adopts the tool
and demonstrably uses it to fulfill a duty more completely or improve a constituent outcome, with
the non-partisan/ethics guardrails independently verified.

---

## Scope

**In scope**

- Guardrail / public-duty policy layer (non-partisan, anti-evasion, anti-surveillance, duty-over-
  optics) enforced at input classification, system-prompt, and output-screening layers.
- Multi-tenant app skeleton (Next.js App Router, TypeScript/ESM, PWA), every row scoped to an
  office/official; AES-256-GCM encryption at rest for sensitive content.
- "Imprint" office-memory layer: duties, statutes/sources (cited), decisions/votes, meetings/events,
  constituent cases, and retrievable notes with vector search.
- Public-service faculties: **Duties & Roles**, **Ethics & Compliance**, **Constituent Casework**,
  **Meeting/Vote Briefings**, plus a duty-focused **daily briefing** and **outcome tracking**.
- One pilot jurisdiction's structured, primary-source-cited civic content, expert-reviewed.
- Eval harness proving memory-grounded, cited output beats blank-slate.
- Data retention + deletion, provenance recording, and an audit log.

**Out of scope (explicitly will NOT do)**

- Campaign strategy, electioneering, partisan messaging, talking points, fundraising, donor
  targeting, voter-file analysis, or **re-election optimization** of any kind.
- **Opposition research** or any analysis of political rivals, challengers, or partisan advantage.
- Helping a user **evade, delay, or minimize** open-meeting, public-records/FOIA/sunshine,
  disclosure, or ethics obligations (e.g., drafting a denial to dodge a valid records request,
  structuring a meeting to avoid a quorum/notice trigger).
- **Constituent surveillance, profiling, political/sentiment targeting, or manipulation**; building
  political contact lists; or any use of constituent data for non-service purposes.
- PR/optics/"spin" optimization, reputation management, or self-promotion content.
- Acting autonomously on the official's behalf (filing, voting, sending, publishing).
- Definitive legal advice, verdicts, or jurisdiction-specific claims that are not sourced to primary
  law and expert-reviewed.

When a request falls in the out-of-scope/refused set, the tool refuses that part, explains why in
public-duty terms, and where possible offers a lawful, transparent alternative (e.g., "I can't help
minimize this records request, but here is how the public-records process works and who can advise
you").

---

## Solution approach & architecture

**Stack.** TypeScript, ESM. Next.js 15 (App Router) + React, deployable as a PWA for offline-
friendly use on a councilmember's phone. PostgreSQL + `pgvector` via Prisma. Anthropic Claude as the
reasoning layer (model selection and pricing per the Claude API skill; all calls behind a thin
provider-neutral LLM client so the core stays vendor-neutral). Clerk for authentication, multi-
tenant from the first commit. AES-256-GCM for sensitive content at rest. Code license **TBD (AGPL
vs MIT — open question)**; civic content **CC-BY-4.0**.

**Components**

1. **Guardrail / public-duty policy layer (`lib/guardrails`) — built first.** A safety-critical
   subsystem, not a prompt suffix. Three enforcement points:
   - *Intent classification*: an input classifier tags requests against a public-duty policy
     taxonomy (allowed service/duty/compliance vs. refused campaign/evasion/surveillance/optics).
     Refused categories never reach a faculty.
   - *System policy*: a `PUBLIC_DUTY_SYSTEM` charter injected into every faculty prompt establishing
     fiduciary-duty framing, non-partisanship, transparency-positive defaults, and hard refusals.
   - *Output screening*: post-generation screening for partisan/targeting/evasion leakage; flags
     route to a review queue and block delivery. All refusals and flags are logged (without storing
     the sensitive content) for audit. This layer ships with its own adversarial red-team suite run
     in CI; a regression that bypasses a refusal **fails the build**.

2. **Imprint — office memory layer (`lib/imprint`).** The inverse of Ofelia's personal memory: it
   stores the *office's* working memory, not a person's leverage. Entities/records: Duties,
   Sources/Statutes (with citation + provenance), Decisions/Votes, Meetings/Events, Constituent
   Cases (PII-minimized, encrypted), and retrievable Notes with 1536-dim embeddings queried via
   pgvector cosine similarity (keyword fallback). Retrieval assembles a cited context block; every
   faculty answer must carry its sources.

3. **Faculties — public-service modules (`lib/faculties`)** behind a router/factory and the
   guardrail layer:
   - **Duties & Roles** — structured, source-cited representation of the office's statutory duties,
     oath, and powers for the pilot jurisdiction.
   - **Ethics & Compliance** — conflict-of-interest, open-meeting/sunshine, public-records, gift
     rules, campaign-vs-official-resource separation, and records retention; flags when a
     contemplated action may violate them. Informational; routes to the ethics board / counsel.
   - **Constituent Casework** — service-oriented case tracking with privacy-first fields only
     (issue, status, next step, resolution); **no political affiliation, no profiling, no
     targeting fields**; encrypted; retention + deletion enforced.
   - **Meeting/Vote Briefings** — balanced, cited briefings that lay out the question, the
     applicable rules, options, and tradeoffs to inform (not replace) the official's judgment;
     explicitly avoids recommendations framed as the "winning" political move.
   - **Daily briefing** — a short, duty-focused digest (upcoming meetings, notice/records
     deadlines, open cases, pending disclosures) — never campaign or optics items.

4. **Outcomes & calibration (`lib/outcomes`, `lib/calibration`).** Tracks constituent-impact
   outcomes and (optionally) forecast calibration for the official's own predictions about
   duty-relevant matters — reframed from personal edge to honest self-assessment and service
   follow-through.

5. **Eval harness (`scripts/eval-grounded.ts`).** Runs faculties memory-grounded vs. blank-slate on
   fixture scenarios; an LLM judge scores accuracy, groundedness/citation, and fit. The headline
   metric is the delta: if grounded + cited does not clearly beat blank-slate, the thesis fails.

**Key decisions**

- Guardrails are a first-class, tested subsystem and a release gate — not documentation.
- Agent-neutral core; any Anthropic/Claude specifics sit behind the LLM client (mirrors Elyos's
  core/adapter rule).
- Depth-first on one jurisdiction with expert sign-off before any breadth.
- Privacy by construction: constituent data model has no political fields to misuse in the first
  place; encryption + retention + deletion are built in, not bolted on.

---

## Data, licensing & compliance

**Source material.** Primary law and official guidance: state statutes and constitutions, municipal
charters and ordinances, state ethics-commission rules and advisory opinions, open-meeting/sunshine
and public-records statutes, records-retention schedules, and official clerk/secretary-of-state
guidance. These are generally government works; many U.S. state statutes/regulations are in the
public domain or are government edicts not subject to copyright (per the *Public.Resource.Org*
edict-of-government principle), but **this varies by state and source** (some states assert
copyright in annotations or compiled codes). **Every source's reuse terms must be verified and
recorded before its content ships**; we cite and link primary law and store provenance (source name,
jurisdiction, citation, retrieval date, URL, license/legal-status note).

**Provenance model.** Each duty/compliance claim is backed by a `Source` record (citation +
provenance + verified legal status). The Duties & Roles and Ethics & Compliance faculties may not
surface a claim without an attached source; a citation-coverage test enforces this.

**Output licensing.** Code: **TBD — AGPL-3.0 vs MIT (open question;** AGPL better protects an open
civic commons from closed re-hosting, MIT maximizes adoption/reuse — needs a governance decision).
Civic content/datasets: **CC-BY-4.0** (attribution to primary sources preserved). Docs: CC-BY-4.0.

**Privacy / PII stance (conservative).** Constituent PII is **minimized by design** — only what is
needed to provide the service (name/contact, the issue, status, next step, outcome). **No political
affiliation, voting history, ideology, or profiling fields exist in the schema.** Sensitive content
is **encrypted at rest (AES-256-GCM)**; every row is tenant-scoped to an office/official. A
**data-retention policy** with automatic minimization and a **constituent/official deletion path**
is required before any real PII is stored. Constituent data is **never** used for political
targeting, surveillance, training, or any non-service purpose — enforced by the guardrail layer and
the schema. No secrets, tokens, or PII are written to logs, receipts, or committed files (Elyos
rule).

**Attribution.** Civic content cites primary sources; redistribution preserves attribution per
CC-BY. Expert reviewers are credited (with consent) in a reviewers ledger.

---

## Quality, review & risk gates

**Risk tier: HIGH** across the legal/ethics/governance surface (per
`docs/good-deed-definition.md`: legal/safety domains require credentialed expert sign-off before
merge). Pure platform/UI/infra tasks are low–medium; anything that states a duty, a legal/ethics
rule, or a jurisdiction-specific obligation is HIGH.

**Required reviews before a deed is "done":**

- **Maintainer** review on all PRs (engineering quality, agent-neutral core, no secrets/PII in
  logs, tests/CI green).
- **Credentialed expert sign-off** — a government-ethics professional and/or a licensed attorney for
  the jurisdiction — recorded before *any* duty/compliance/jurisdiction content ships. No expert,
  no ship.
- **Guardrail/red-team review** — the adversarial misuse suite passes in CI **and** an independent
  reviewer audits refusal behavior before the guardrail layer or any new faculty is released.
- **Privacy review** for anything touching constituent data (PII minimization, encryption,
  retention, deletion).

**Every duty/compliance surface is labeled "Informational, not legal advice"** and routes the user
to counsel / the ethics board / the clerk for binding determinations.

**Definition of Shipped (project):** adopted by a real official/office (pilot) and demonstrably used
to fulfill a duty more completely or improve a constituent outcome, with non-partisan/ethics
guardrails verified by an independent government-ethics reviewer, all shipped legal content
expert-signed-off and primary-source-cited, and the privacy controls in force.

---

## Roadmap & milestones

Phased: guardrails + skeleton first; faculties and content only behind the guardrails; pilot
adoption last and gated on a secured partner.

- **M0 — Guardrails & skeleton (cold-start).**
  *Goal:* the safety subsystem and an agent-neutral, multi-tenant skeleton exist before any feature.
  *Exit:* guardrail policy spec + policy layer merged with an adversarial red-team suite passing in
  CI (no known bypass); monorepo + CI green; tenant-scoped data model + at-rest encryption in place;
  "informational, not legal advice" framing wired in.

- **M1 — Imprint (office memory) + privacy foundation.**
  *Goal:* cited office-memory layer with privacy-first constituent model.
  *Exit:* duties/sources/decisions/cases/notes models + vector retrieval working on fixtures;
  PII-minimized constituent schema (no political fields); encryption, retention, and deletion paths
  implemented and tested; privacy review passed.

- **M2 — Duties & Roles + Ethics & Compliance (expert-gated content).**
  *Goal:* the two HIGH-tier faculties, mounted behind guardrails, with one pilot jurisdiction's
  cited content.
  *Exit:* faculties return only source-cited claims (citation-coverage test passing); one
  jurisdiction's Duties & Roles and core Ethics/Compliance content drafted, primary-source-cited,
  and **expert-signed-off**; guardrails verified on these surfaces.

- **M3 — Casework, Briefings, briefing & outcomes.**
  *Goal:* service-oriented modules and the outcomes loop.
  *Exit:* privacy-first casework tracker; balanced/cited meeting-vote briefings (no political
  recommendations); duty-focused daily briefing; constituent-impact outcome tracking — all behind
  guardrails and privacy controls.

- **M4 — Eval, hardening & pilot readiness.**
  *Goal:* prove the thesis and harden for a real user.
  *Exit:* eval shows grounded+cited clearly beats blank-slate; expanded red-team suite green;
  accessibility (WCAG 2.2 AA) + PWA + deletion/retention verified; pilot onboarding runbook ready.

- **M5 — Pilot adoption & handoff (the deed).**
  *Goal:* a real office adopts and benefits.
  *Exit (Definition of Shipped):* a secured pilot official uses the tool to fulfill a duty more
  completely or improve a constituent outcome; guardrails independently verified; content
  expert-signed-off; outcomes recorded. *(Gated on a secured partner — TO BE SECURED.)*

- **M6 — Sustain & scale (post-delivery).**
  *Goal:* durable maintenance and (only then) careful expansion to a second jurisdiction.
  *Exit:* maintenance rotation + ops runbook + outcome dashboard; second-jurisdiction expansion
  process defined and expert-gated.

Dependencies flow M0 → M1 → M2 → M3 → M4 → M5; M2 content tasks block on M0 guardrails and the
secured expert reviewer; M5 blocks on a secured pilot office.

---

## Work breakdown

The itemized, schema-mapped backlog lives in **`TASKS.md`**: ~19 tasks across milestones M0–M6 plus
a future backlog, each mapped to the Elyos Task JSON schema, with per-task acceptance criteria for
the most important items, milestone Definitions of Done, and a complete example Task JSON for the
first M0 task (the guardrail policy spec). The first build item in TASKS.md is the guardrail / public-
duty policy specification, reflecting its status as a hard product requirement.

---

## Governance, roles & stakeholders

- **Maintainer (Owner): TBD.** Owns architecture, the agent-neutral core, CI, and merge quality.
- **Reviewers / rotation:** at least one engineering reviewer plus a designated **guardrail/red-team
  reviewer** who audits refusal behavior independently of feature authors.
- **Credentialed expert reviewers (HIGH tier): TO BE SECURED** — a government-ethics professional
  and/or a licensed attorney for the pilot jurisdiction; signs off all duty/compliance/jurisdiction
  content before it ships. Tracked in a reviewers ledger with credentials and consent.
- **Steward (last-mile owner): TO BE SECURED** — owns the pilot relationship and the
  hand-off/adoption that constitutes shipping.
- **Partner / requestor: TO BE SECURED** — the pilot office/official or sponsoring civic
  organization (municipal league, clerks' association, good-government NGO, or public-administration
  program).
- **Community / board:** edge-cases and the AGPL-vs-MIT license decision go through Elyos governance.

---

## Dependencies & integrations

- **External services:** Anthropic Claude API (reasoning, behind the neutral LLM client); Clerk
  (auth/multi-tenant); managed PostgreSQL with `pgvector`; hosting/PWA delivery.
- **Datasets / sources:** the pilot jurisdiction's primary law and official guidance (statutes,
  charter/ordinances, ethics rules + advisory opinions, open-meeting/records statutes, retention
  schedules) — each with verified reuse terms and recorded provenance.
- **Upstream/reference:** the Ofelia app (`C:\code\Ofelia`) as the architectural basis to adapt and
  invert; public-domain legal corpora (e.g., Public.Resource.Org) for sourcing.
- **Elyos pieces:** `packages/schema` (Task JSON), `CLAUDE.md` work rules + refusal guardrails,
  `docs/good-deed-definition.md` (risk tiers), Elyos governance for license/edge-case decisions.
- **Human dependencies (critical path):** a secured credentialed expert reviewer (blocks M2 content)
  and a secured pilot office/steward (blocks M5).

---

## Risks & mitigations

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Tool is steered to partisan/campaign/electioneering use | High | Critical | Guardrail layer built first; intent classifier + system policy + output screening; adversarial red-team suite gates CI; independent reviewer audit; refused categories never reach a faculty | Guardrail reviewer |
| Used to evade transparency/open-records/ethics law | Medium | Critical | Transparency-positive defaults; hard refusal of evasion requests with lawful-alternative redirect; red-team coverage; expert review of compliance content | Guardrail reviewer / Expert |
| Constituent data used for surveillance/profiling/targeting | Medium | Critical | Schema has no political/profiling fields; PII minimized + encrypted; retention + deletion; guardrail prohibits non-service use; privacy review gate | Maintainer / Steward |
| Inaccurate or outdated jurisdiction-specific legal claim | High | High | Primary-source citation required (coverage test); credentialed expert sign-off before ship; "informational, not legal advice"; dated sources + review cadence | Expert reviewer |
| No pilot office secured → cannot reach Definition of Shipped | High | High | Honest `TO BE SECURED`/`verifiedNeed:false`; build platform + one illustrative jurisdiction meanwhile; pursue municipal leagues / NGOs / academic partners early | Steward / Maintainer |
| No credentialed expert secured → M2 content blocked | Medium | High | Recruit via public-administration programs, bar associations, ethics commissions; do not ship HIGH content without sign-off (hard gate) | Maintainer |
| Source license/copyright on compiled codes/annotations | Medium | Medium | Verify + record reuse terms per source before shipping; prefer edict-of-government primary law; cite, don't copy proprietary annotations | Expert / Maintainer |
| Over-reliance: official treats output as legal advice | Medium | High | Persistent "informational, not legal advice" labeling; route to counsel/ethics board; briefings inform not decide | Maintainer / Expert |
| Multi-tenant data leakage across offices | Low | Critical | Tenant scoping on every row + query; tests for isolation; least-privilege auth | Maintainer |
| LLM hallucination of duties/citations | Medium | High | Retrieval-grounded answers only; no-source-no-claim rule; eval harness; output screening | Maintainer |

---

## Security & privacy

**Threat surface.** Misuse for partisan/political ends (primary threat); cross-tenant data leakage;
exposure of constituent PII; exfiltration of sensitive case content; prompt-injection attempting to
bypass the guardrail layer; secrets leakage.

**Controls.** Guardrail layer as a safety-critical, adversarially tested subsystem (the top
control). Multi-tenant isolation — every row scoped by office/official, enforced in queries and
tested. AES-256-GCM encryption at rest for sensitive content; encryption key never committed.
Clerk-based auth with least privilege. **PII minimization by schema** (no political/profiling
fields) plus retention limits and a deletion path. Output screening blocks partisan/targeting/
evasion leakage. **No secrets, tokens, or PII in logs, receipts, or committed files** (Elyos rule);
guardrail logs record refusal reasons/flags, not the sensitive content. Prompt-injection resistance:
the policy layer is enforced server-side and cannot be overridden by user/document content; the
red-team suite includes injection attempts. Dependency and secret scanning in CI.

**Abuse/misuse prevention.** The refused-use set (campaign, electioneering, fundraising, opposition
research, re-election optimization, transparency/records/ethics evasion, constituent surveillance/
profiling/targeting/manipulation, optics/spin) is enforced, tested, and logged — not merely
documented — and the tool never acts autonomously on the official's behalf.

---

## Sustainability & maintenance

After delivery, a named **maintenance rotation** owns the platform; the **steward** owns the pilot
relationship and outcome tracking. Civic content carries a **review cadence** (law changes; sources
re-verified and re-dated) — expert sign-off is required again for material legal updates. Outcomes
are tracked in-app (cases resolved, duty/compliance improvements, guardrail-audit status) and
surfaced on an outcomes dashboard — **not** engagement metrics. Expansion to a second jurisdiction
follows a documented, expert-gated process and only after the first is stable. The guardrail
red-team suite is maintained as living tests and expanded as new misuse vectors are found.

---

## Open questions

- **Code license: AGPL-3.0 vs MIT?** AGPL protects an open civic commons from closed re-hosting;
  MIT maximizes reuse/adoption. Needs an Elyos governance decision. (Content: CC-BY-4.0.)
- **Which pilot jurisdiction / office type first?** Choice drives the entire content corpus and
  expert reviewer profile. TO BE SECURED.
- **How is the credentialed expert reviewer compensated/credited,** and how is independence ensured?
- **State-by-state source reuse terms** — which jurisdictions' compiled codes/annotations carry
  copyright constraints that limit reuse?
- **Lane:** donated by default; is there a future funded lane for expert review hours (with a hard
  budget cap) without compromising independence?
- **Constituent consent & records-law interaction** — how does casework data interact with public-
  records obligations (some constituent communications may themselves be public records)?
- **Scope of calibration/predictions** — keep, or drop as not core to fiduciary duty?

---

## References

- Proposal: `governance/proposals/public-official-guide.md`
- Elyos work rules & refusal guardrails: `CLAUDE.md`
- Good-deed definition & risk tiers: `docs/good-deed-definition.md`
- Task JSON schema: `packages/schema/src/schemas.ts`
- Architectural basis (to adapt + invert): Ofelia app at `C:\code\Ofelia`
  (`src/lib/faculties/*`, `src/lib/imprint/*`, `src/lib/guardrails`, `prisma/schema.prisma`,
  `scripts/eval-leverage.ts`)
- Sibling Elyos plan for house style: `planning/projects/beacon-game/{PLAN,TASKS}.md`
- Edict-of-government doctrine (source reuse): *Georgia v. Public.Resource.Org* (U.S. 2020)
