# Proposal: public-official-guide

**Proposer:** jdev1977 (drafted by Claude Code)
**Date:** 2026-06-28
**Domain(s):** civic, governance, public-service, software
**Lane:** donated
**Requestor / beneficiary:** elected & appointed public officials (esp. local/under-resourced offices) and, through them, their constituents  ·  **Verified need:** TO BE SECURED (pilot office)

## Summary
An open, **non-partisan** AI guide that helps public and elected officials do their job
optimally — understand and fulfill their statutory duties, serve constituents well, and govern
ethically and transparently. It reuses the architecture of the Ofelia app (a private long-horizon
memory layer + specialized AI "faculties" + calibrated predictions + outcome tracking + briefings)
but **deliberately inverts its purpose**: from *personal advantage* to *public duty*.

## The defining design constraint (read first)
Ofelia optimizes for one person's advantage. A tool that did that for an elected official would be
harmful. Public-Official-Guide is built on the opposite premise — the official holds a **fiduciary
duty to constituents and the public interest** — and it is engineered to refuse misuse:

- **Non-partisan.** No campaign strategy, electioneering, partisan messaging, opposition research,
  fundraising, or re-election optimization. It serves the *office*, not the *politician*.
- **Pro-transparency & accountability.** It encourages disclosure, open meetings, and public
  records compliance; it never helps evade them.
- **Pro-compliance.** Surfaces conflict-of-interest, ethics, gift, campaign-vs-official-resource,
  and records-retention rules — and flags when a contemplated action may violate them.
- **No constituent surveillance or manipulation.** Constituent data is for service and casework,
  never profiling, targeting, or political use.
- **Duty over optics.** Optimizes for constituent outcomes and lawful duty, not PR or spin.

## Why it qualifies as a good deed
- **Tangible public benefit:** better-informed, more ethical, more responsive governance improves
  constituents' lives — especially in small/under-resourced offices with no staff.
- **Freely available:** open source (e.g., AGPL/MIT TBD); open civic content under CC-BY.
- **Not primarily for-profit:** serves officials' public duty and the public; no political clients.
- **No harm/misinformation:** non-partisan, source-cited to actual statutes/charters, with hard
  refusals for political/advantage misuse; "informational, not legal advice."
- **Executable by AI sessions:** decomposes into app modules and per-jurisdiction civic content,
  with expert (legal/ethics) review where the risk tier requires it.

## Scope / first tasks
- (medium) App skeleton (Next.js/TS, PWA), with the non-partisan/ethics **guardrail layer first**.
- (medium) "Duties & roles" knowledge module: structured, cited representation of an office's
  statutory duties, oath, and powers for one pilot jurisdiction.
- (small) Ethics/compliance checker: COI, open-meeting, records-retention, gift rules (informational).
- (medium) Constituent casework tracker (service-oriented; privacy-first; no political fields).
- (small) Meeting/vote briefing generator (cited, balanced, options + tradeoffs, not recommendations
  that substitute for the official's judgment).

## Definition of shipped
Adopted by a real official/office (pilot) and demonstrably used to improve a constituent outcome or
fulfill a duty more completely — with the non-partisan/ethics guardrails verified by an independent
government-ethics reviewer.

## Risks / review needs
**Risk tier: HIGH** in the legal/ethics/governance surface. Requires **credentialed expert review**
(government-ethics professional and/or licensed attorney for the jurisdiction) before any
duty/compliance content ships. Always labeled **informational, not legal advice**. Jurisdiction
accuracy is hard and must be sourced to primary law. **Misuse is the top risk** — the guardrail
layer (non-partisan, anti-evasion, anti-surveillance) is a product requirement, adversarially
tested, not a disclaimer. Privacy: constituent PII minimized, encrypted at rest, never used politically.
