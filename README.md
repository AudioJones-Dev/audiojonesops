# audiojonesops

**The canonical operations repository for Audio Jones / AJ Digital.**

This repo is the single source of truth for how AJ Digital runs its marketing and sales engine. All approved operating docs, SOPs, templates, and tracking standards live here. If a process isn't written down here, it isn't canonical.

---

## Purpose

`audiojonesops` houses the operating system for the business across six domains:

- **Marketing operations** — brand, messaging, positioning, content production systems, and the workflows that turn ideas into published assets.
- **Sales operations** — pipeline, qualification, outreach, and the path from attention to qualified conversation to closed work.
- **Social media management** — channel strategy, posting cadence, engagement standards, and the production lines feeding each platform.
- **Content systems** — repeatable production workflows (briefs → research → script → design → publish), templates, and evidence standards.
- **Campaign SOPs** — standard operating procedures for individual campaigns and recurring content formats.
- **Analytics and performance tracking** — how results are captured, which metrics matter, and how reviews drive optimization.

---

## Operating principles

These hold across every domain and SOP in this repo:

- **One source of truth.** Everything approved lives here in Markdown. The repo is the canonical record, not chat threads or scattered docs.
- **Evidence discipline.** No public statistic is used unless it meets the Tier 1 evidence bar (primary/authoritative, verifiable, current, accurately quoted).
- **Human approval gates.** Work advances through explicit sign-off, not by default.
- **Qualified conversation is the primary metric.** Vanity signals explain results; they never declare success.
- **AJ Digital language.** Founder Intelligence Systems, Revenue Leak Diagnostics, Operational Intelligence, Business Memory, Signal vs Noise. No public-facing agent/automation jargon.

---

## Canonical documents

| Document | Domain | Status |
|---|---|---|
| [`CAROUSEL_PRODUCTION_SOP.md`](./CAROUSEL_PRODUCTION_SOP.md) | Content systems / Social media | V0 (Manual) — active |
| [`docs/security/remote-secret-operations.md`](./docs/security/remote-secret-operations.md) | Security / Agent operations | Required control |
| [`INITIAL_REPO_STATUS.md`](./INITIAL_REPO_STATUS.md) | Repo meta | Reference |

This table grows as new SOPs and systems are added.

---

## How this repo is organized

The repo is intentionally lightweight today and will expand as operations are codified. Conventions:

- Top-level `*_SOP.md` files are canonical standard operating procedures.
- Security doctrine lives under `docs/security/`.
- Each major content/campaign system owns a folder for its working artifacts (briefs, research, scripts, handoffs, analytics).
- Reviews (weekly/monthly) and shared evidence libraries live in their own folders as they come online.

See each SOP's "Folder / database structure" section for the layout it expects.

---

## Contributing changes

1. Develop on a feature branch.
2. Keep changes scoped to one system or SOP per branch where possible.
3. Open a pull request into `main` for review and approval before merge.
4. Once approved and merged, the doc is canonical.
