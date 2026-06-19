# AGENTS.md - Operating Contract for audiojonesops

This file is the canonical operating contract for any AI agent or human
working in this repository. It defines who does what, in what order, and
how changes reach `main`. If behavior in a session conflicts with this
file, this file wins and the behavior is corrected.

This repo is a canonical operations repository: Markdown SOPs, specs, and
tracking standards. It is not primarily an application or code repo. The
main risk is coordination drift, not technical complexity, so the lanes
below are strict.

---

## Roles and lanes

### Claude - planning, synthesis, operations design, first-draft docs

Owns: PRDs, SOP drafts, campaign logic, planning, decision logs, and
business-language refinement.

Claude does not:

- Run Git operations (branch, commit, push, PR) as a default.
- Assume the contents of repo files beyond what is explicitly provided.
- Claim implementation is complete. A drafting pass is a drafting pass.

Every Claude deliverable is a Git-Spec-ready Markdown draft in the format
below, handed off for Codex to review and implement.

### Codex - repo truth, review, Git operations, validation, controlled implementation

Owns: inspecting actual repo state, comparing drafts against existing
files, flagging conflicts, creating branches, applying approved edits,
running checks, verifying `git diff` / structure / links / status, and
preparing PRs.

Codex is the only agent that asserts what is actually on `main`.

### Human operator - approval gates

Approves movement between phases:

1. Draft accepted
2. Repo edit approved
3. PR approved
4. Merge approved

No phase advances without the corresponding approval.

---

## Default sequence

1. Claude produces the spec or draft.
2. Human pastes Claude's output into Codex.
3. Codex reviews it against the repo and flags conflicts or overlap.
4. Codex creates the feature branch.
5. Codex applies only approved edits.
6. Codex verifies `git diff`, file structure, links, and status.
7. Codex opens or prepares a PR.
8. Claude may review final wording only after Codex reports the exact diff.

Claude-first, Codex-second is the default order. Use Codex-first only when
the unit is Git/state/validation-heavy: branch cleanup, repo structure
checks, PR prep, file movement, or verifying what is actually on `main`.

Do not let Claude and Codex edit the same branch casually. That is how
docs repos become messy.

---

## Branch rule

Use one branch per operational unit. Use descriptive, scoped names:

```txt
docs/carousel-system-v1
docs/sales-ops-sop
docs/content-tracker-schema
ops/repo-structure-baseline
```

Avoid broad, unclear branches:

```txt
update-docs
ops-cleanup
claude-edits
```

Changes reach `main` only via feature branch -> pull request ->
human-approved merge. `main` is the canonical trunk and is never edited
directly.

---

## Spec format

Every planning or drafting deliverable from Claude must include, in order:

1. Problem
2. Desired outcome
3. Success criteria
4. Scope
5. Out of scope
6. Constraints
7. Existing repo docs to inspect
8. Proposed file changes
9. Risks
10. Open questions
11. Final Markdown draft

Claude proposes the exact branch name for Codex to create. Claude does not
create it.

---

## Operating principles

These hold across every SOP and system here. See `README.md` for the full
repo context.

- One source of truth: approved docs live here, stated once, never duplicated.
- Evidence discipline: no public statistic unless it meets the Tier 1 evidence bar.
- Human approval gates: work advances by sign-off, not by default.
- Qualified conversation is the primary success metric.
- AJ Digital language: no public-facing agent or automation jargon in outward content.
