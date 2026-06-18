# CAROUSEL_PRODUCTION_SOP

**Document type:** Standard Operating Procedure
**Owner:** Audio Jones (AJ Digital)
**Derived from:** `CAROUSEL_INTELLIGENCE_SYSTEM_PRD.md`
**Status:** V0 (Manual) — active for first 30 days
**Last updated:** 2026-06-18

---

## 1. Purpose

This SOP translates the approved Carousel Intelligence System PRD into a repeatable weekly operating workflow.

The objective is a predictable production line that ships LinkedIn/Instagram carousels which:

- Position AJ Digital around **Founder Intelligence Systems**, **Revenue Leak Diagnostics**, **Operational Intelligence**, **Business Memory**, and **Signal vs Noise**.
- Move the right founders from passive scrolling to a **qualified conversation**.
- Are produced on a fixed cadence without quality drift, regardless of how busy the week is.

**Primary success metric:** *Qualified conversation initiated* — a real exchange with a founder who fits the buyer profile and who reached out (or replied) as a direct result of a carousel.

Secondary signals (saves, profile visits, DM volume, follower quality) are diagnostic only. They explain *why* the primary metric moved; they never replace it.

This document governs **how** carousels get made. The PRD governs **why** and **what**. If the two ever conflict, the PRD wins and this SOP is corrected.

---

## 2. Required tools

| Function | Tool (V0) | Notes |
|---|---|---|
| Canonical docs + this SOP | Repo / vault (Markdown) | Single source of truth. Everything approved lives here. |
| Drafting + scripting | Claude (project docs workspace) | Briefs, research, slide scripts, copy. |
| Evidence + research capture | Repo `research/` + source links | Every stat traced to a source. |
| Design / slide build | Canva (or Figma) | Brand template kit, locked styles. |
| Scheduling / queue | Native platform + manual calendar | **No auto-publish in V0.** |
| Analytics capture | Platform analytics + manual log | Logged by hand into the tracker. |
| Tracker | Spreadsheet or Airtable/Notion base | One row per carousel. |

V0 deliberately runs on the smallest possible toolchain. Automation is added only in V1, and only where a manual step has proven stable for 30 days.

---

## 3. Folder / database structure

Canonical structure inside the repo/vault:

```
/audiojonesops
├── CAROUSEL_INTELLIGENCE_SYSTEM_PRD.md      # source of truth (why/what)
├── CAROUSEL_PRODUCTION_SOP.md               # this file (how)
├── /carousels
│   ├── /_templates                          # all blank templates from this SOP
│   ├── /backlog                             # approved ideas not yet scheduled
│   ├── /in-production                       # active week's carousels
│   │   └── /YYYY-WW-slug                     # one folder per carousel
│   │       ├── 00-brief.md
│   │       ├── 01-research.md
│   │       ├── 02-slide-script.md
│   │       ├── 03-design-handoff.md
│   │       └── 04-publish-and-analytics.md
│   ├── /published                           # shipped, archived by month
│   └── /retired                             # killed or deprecated ideas
├── /research
│   └── evidence-library.md                  # Tier 1 evidence, reusable
└── /reviews
    ├── /weekly                              # weekly review notes
    └── /monthly                             # monthly optimization notes
```

### Tracker (database) schema

One row per carousel:

| Field | Description |
|---|---|
| Carousel ID | `YYYY-WW-slug` |
| Title / hook | Working title |
| Topic cluster | Must map to one PRD cluster |
| Framework | The AJ framework featured |
| Buyer pain | The specific pain addressed |
| CTA | The single ask |
| Evidence tier | Tier 1 only for public stats |
| Status | Backlog → Brief → Research → Script → Design → Approved → Scheduled → Published |
| Approval gates | G1–G4 (date + approver) |
| Publish date | Actual |
| Qualified conversations | Count attributed |
| Saves / profile visits / DMs | Secondary signals |
| Notes | Learnings |

---

## 4. Weekly production cadence

**V0 throughput: 2 carousels/week for 30 days. Hold this line. Do not scale until the 30-day review.**

The week runs on a fixed rhythm so production never collides with publishing.

| Day | Block | Output |
|---|---|---|
| **Monday** | Plan + Brief | 2 carousel briefs drafted and submitted to **Gate 1**. |
| **Tuesday** | Research | 2 research briefs completed; all evidence verified Tier 1. **Gate 2**. |
| **Wednesday** | Script | 2 slide scripts written. **Gate 3 (copy)**. |
| **Thursday** | Design | 2 design handoffs built; designs returned. **Gate 4 (final)**. |
| **Friday** | Publish + Log | Approved carousels published **manually**; analytics baseline logged. |
| **Rolling** | Engage | Reply to every comment/DM; flag qualified conversations in tracker. |

Publishing slots in V0: **2 per week**, spaced (e.g. Tuesday + Thursday, or Wednesday + Friday) so the prior week's two carousels publish while the current week's two are produced. Pick the two slots once and keep them fixed for the 30 days.

---

## 5. V0 manual workflow (current — first 30 days)

V0 is fully human-driven. Claude assists with drafting; the operator (Audio) reviews and approves every artifact before it advances.

**Step-by-step, per carousel:**

1. **Select topic** from the approved backlog. Confirm it maps to a topic cluster, framework, buyer pain, and CTA. If any of the four is missing, it is not ready — send it back to backlog.
2. **Write the carousel brief** (Section 8 template) in `00-brief.md`. → **Gate 1**.
3. **Run research** (Section 10 template) in `01-research.md`. Every public statistic must be **Tier 1 evidence** or it is cut. → **Gate 2**.
4. **Write the slide script** (Section 11 template) in `02-slide-script.md`. → **Gate 3**.
5. **Build the design handoff** (Section 12 template) in `03-design-handoff.md`. Design is built in Canva/Figma from the brand kit. → **Gate 4**.
6. **Publish manually.** A human posts the carousel at the scheduled slot. **No automation publishes in V0.**
7. **Log analytics** (Section 14 checklist) in `04-publish-and-analytics.md` and the tracker.
8. **Engage** every comment and DM; record any qualified conversation.

Rules for V0:

- 2/week, no more. Throughput discipline is the point of V0.
- No auto-publishing. Every post is placed by a human.
- No public statistic ships unless Tier 1.
- Every carousel maps to cluster + framework + pain + CTA. No exceptions.

---

## 6. V1 semi-automated workflow (future — only after 30-day review)

V1 is **not active**. It is documented so the path is clear. V1 may begin only when V0 has run a full 30 days and the monthly review approves the move.

What V1 adds — and **only** where the manual step proved stable:

- **Assisted drafting at scale:** Claude pre-fills briefs, research, and scripts from the backlog; the operator edits rather than writes from scratch.
- **Evidence library reuse:** verified Tier 1 evidence is pulled from `research/evidence-library.md` instead of re-sourced each time.
- **Templated design generation:** structured slide scripts feed a locked brand template to produce first-draft designs faster.
- **Scheduling queue:** carousels may be queued in a scheduler — **but a human still presses publish or approves the queued send.** Throughput may rise toward 3/week if quality holds.

What V1 does **not** change:

- The four human approval gates remain.
- The Tier 1 evidence rule remains absolute.
- The cluster + framework + pain + CTA mapping remains mandatory.
- The primary metric remains *qualified conversation initiated*.

**No fully autonomous publishing.** Even in V1, a human owns the publish decision.

---

## 7. Human approval gates

Four gates. Nothing advances without sign-off. Approver in V0 is Audio.

| Gate | When | Question answered | Pass criteria |
|---|---|---|---|
| **G1 — Brief** | After brief | Is this worth making? | Maps to cluster + framework + pain + CTA; audience and angle are clear. |
| **G2 — Evidence** | After research | Is every claim defensible? | Every public stat is **Tier 1**; non-Tier-1 claims removed or reframed as opinion. |
| **G3 — Copy** | After script | Does it say the right thing the right way? | Hook earns the swipe; uses AJ language; single CTA; no public-facing agent jargon. |
| **G4 — Final** | After design | Is it ready to ship? | On-brand, legible, slide order correct, CTA present, links/handles correct. |

Gate logging: each gate records **date + approver + decision (approve / revise / kill)** in the tracker. A "revise" returns the artifact to its author with notes; it does not skip forward.

---

## 8. Carousel brief template

```markdown
# Carousel Brief — [Working Title]
Carousel ID: YYYY-WW-slug
Date: 
Author: 

## Mapping (all four required)
- Topic cluster: 
- Framework featured: [Founder Intelligence Systems | Revenue Leak Diagnostics | Operational Intelligence | Business Memory | Signal vs Noise]
- Buyer pain addressed: 
- Call to action (single): 

## Audience
- Who this is for (founder profile): 
- What they currently believe: 
- What they should believe after: 

## Angle
- Core idea in one sentence: 
- Why now: 
- The shift we create (before → after): 

## Success
- Primary: qualified conversation initiated
- What a qualified reply looks like for this piece: 

## Constraints check
- [ ] Maps to a topic cluster
- [ ] Maps to a framework
- [ ] Maps to a buyer pain
- [ ] Has exactly one CTA
- [ ] No reliance on non-Tier-1 stats

## Gate 1 decision
- Approver / Date / Decision:
```

---

## 9. Research brief template

> See Section 10. (The research brief *is* the research deliverable; this section pointer is kept so the numbered list matches the PRD's required contents.)

---

## 10. Research brief template

```markdown
# Research Brief — [Working Title]
Carousel ID: YYYY-WW-slug
Date: 
Researcher: 

## Claims to support
List every factual claim the carousel will make.
1. 
2. 

## Evidence (Tier 1 only for public statistics)
| Claim | Source | Tier | Link | Date checked | Verbatim figure |
|-------|--------|------|------|--------------|-----------------|
|       |        |      |      |              |                 |

### Tier 1 definition (must pass ALL)
- Primary or authoritative source (original study, official data, named first-party).
- Verifiable: a working link or document a third party can open.
- Current / clearly dated; not stale or context-stripped.
- Quoted accurately — figure and framing match the source.

> If a public statistic is not Tier 1, it is CUT or reframed as clearly-labeled opinion. No exceptions.

## Buyer pain validation
- Evidence this pain is real for our founder profile: 
- AJ framing of the pain (Revenue Leak / Signal vs Noise / etc.): 

## Reusable?
- [ ] Add verified Tier 1 items to research/evidence-library.md

## Gate 2 decision
- Approver / Date / Decision:
```

---

## 11. Slide script template

```markdown
# Slide Script — [Working Title]
Carousel ID: YYYY-WW-slug
Slides: 6–10 recommended
Voice: AJ Digital — direct, diagnostic, founder-to-founder. No public-facing agent jargon.

## Slide 1 — Hook (earns the swipe)
- On-slide text: 
- Subtext (optional): 

## Slide 2 — Stakes / the pain named
- On-slide text: 
- Framework lens: 

## Slides 3–N — The intelligence (one idea per slide)
- Slide 3: 
- Slide 4: 
- Slide 5: 
- (Each slide: one idea. Use Tier 1 evidence where a stat appears.)

## Slide N-1 — The shift (Signal vs Noise / before → after)
- On-slide text: 

## Final slide — Single CTA
- The one ask: 
- What happens when they take it: 

## Caption
- Hook line: 
- Body (expands the idea, not a transcript of slides): 
- CTA repeated once: 
- 3–5 relevant terms (no spam):

## Language check
- [ ] Uses AJ language (Founder Intelligence Systems / Revenue Leak Diagnostics / Operational Intelligence / Business Memory / Signal vs Noise) where natural
- [ ] No public-facing agent/automation jargon
- [ ] Exactly one CTA

## Gate 3 decision
- Approver / Date / Decision:
```

---

## 12. Design handoff template

```markdown
# Design Handoff — [Working Title]
Carousel ID: YYYY-WW-slug
Builder: 
Source script: 02-slide-script.md

## Specs
- Platform(s): LinkedIn / Instagram
- Dimensions: 1080x1350 (4:5) [confirm per platform]
- Slide count: 
- Brand kit: [link to locked template]

## Per-slide layout
| Slide | Headline text | Supporting text | Visual / asset | Notes |
|-------|---------------|-----------------|----------------|-------|
| 1     |               |                 |                |       |
| 2     |               |                 |                |       |

## Brand rules
- Fonts / colors: locked from brand kit
- Logo / handle placement: 
- Accessibility: legible at thumbnail size, high contrast

## Asset list
- Images / icons / charts needed: 
- Source + license for each: 

## CTA slide
- Exact CTA text: 
- Handle / link shown: 

## Gate 4 (final) decision
- Approver / Date / Decision:
```

---

## 13. Publishing checklist

**Manual publish only in V0. A human posts every carousel.**

```markdown
# Publish Checklist — YYYY-WW-slug
- [ ] Gate 4 passed (final design approved)
- [ ] Correct platform account selected
- [ ] Slides in correct order; first slide is the hook
- [ ] Caption pasted; hook line leads; single CTA present
- [ ] Handle / link correct and tested
- [ ] Terms/tags reviewed (relevant, not spammy)
- [ ] Scheduled slot is one of the two fixed weekly slots
- [ ] Published by a human at the slot (NO auto-publish)
- [ ] Post URL captured into 04-publish-and-analytics.md
- [ ] Tracker status set to "Published" with date
```

---

## 14. Analytics logging checklist

Log a baseline within 24 hours of publishing, then again at the weekly review (≈7 days).

```markdown
# Analytics Log — YYYY-WW-slug
Post URL: 
Published: [date/time]

## Primary metric
- Qualified conversations initiated (count): 
- Source of each (comment / DM / profile → reply): 
- Notes on fit (did they match the buyer profile?): 

## Secondary signals (diagnostic only)
- Impressions / reach: 
- Saves: 
- Profile visits: 
- DMs received: 
- Follower change (quality noted): 

## Snapshots
- 24h baseline: 
- 7-day: 

## Read-out
- What this carousel suggests about cluster/framework/pain/CTA: 
- One thing to repeat: 
- One thing to change: 
```

---

## 15. Weekly review process

**When:** Friday (or first working day after the week's second publish).
**Where:** `reviews/weekly/YYYY-WW.md`.
**Goal:** Learn from the two carousels and confirm next week's two are ready.

Agenda:

1. **Primary metric first.** How many qualified conversations did this week's carousels initiate? From which pieces?
2. **Pattern check.** Which cluster / framework / pain / CTA combinations are producing conversations vs silence?
3. **Quality gate audit.** Did anything slip a gate? Any non-Tier-1 stat almost ship? Fix the process, not just the post.
4. **Secondary signals as explanation only.** Use saves/visits/DMs to explain the primary result, never to declare success on their own.
5. **Next week locked.** Confirm 2 briefs are approved (G1) and ready to enter production Monday.
6. **Backlog hygiene.** Add new ideas; retire dead ones.

Output: a short written review + updated tracker. No carousel counts as "reviewed" until its 7-day analytics are logged.

---

## 16. Monthly optimization process

**When:** End of each 30-day cycle (the first one closes the V0 trial).
**Where:** `reviews/monthly/YYYY-MM.md`.

Agenda:

1. **Cumulative primary metric.** Total qualified conversations over the month, by cluster / framework / pain / CTA. What converts?
2. **Winners and losers.** Top 2 and bottom 2 carousels. Why? Document the pattern.
3. **Evidence library.** Promote reusable Tier 1 evidence; purge anything now stale.
4. **Throughput decision.** Was 2/week sustainable at quality? Only here may a change in cadence or a move toward V1 be approved.
5. **Template tune-up.** Update the templates in this SOP based on what actually worked. Version-bump the doc.
6. **Constraint reaffirmation.** Re-confirm: manual publish (V0), Tier 1 only, four-way mapping, single CTA, AJ language, no public-facing agent jargon.

Output: a decision log. Any change to cadence, tooling, or the move to V1 is recorded here with a rationale tied to the primary metric.

---

## 17. Failure modes and mitigations

| # | Failure mode | Signal | Mitigation |
|---|---|---|---|
| 1 | Stat can't be verified to Tier 1 | Research stalls; only secondary sources | Cut the stat or reframe as labeled opinion. G2 blocks it. Never ship unverified public stats. |
| 2 | Carousel doesn't map to all four (cluster/framework/pain/CTA) | Brief feels vague | G1 rejects it. Return to backlog until all four are explicit. |
| 3 | Throughput pressure → scaling past 2/week in V0 | Temptation to "batch ahead" | Hold the line. 2/week for 30 days is the experiment. Cadence change only at monthly review. |
| 4 | Accidental auto-publish | Scheduler used in V0 | V0 forbids auto-publish. Human posts every piece. Scheduler stays off until V1 is approved. |
| 5 | Multiple CTAs / unclear ask | Script has 2+ asks | G3 enforces exactly one CTA. Cut the rest. |
| 6 | Public-facing agent / automation jargon leaks into copy | Words like "agent", "bot", "automation pipeline" on-slide | G3 language check. Speak founder-to-founder in AJ terms. |
| 7 | Vanity metrics declared as success | Review celebrates saves/reach | Primary metric is qualified conversations. Secondary signals explain, never declare. |
| 8 | Brand drift in design | Off-template fonts/colors | G4 enforces locked brand kit. Reject and rebuild. |
| 9 | Engagement not tracked → conversations lost | DMs/comments unanswered | Daily engagement block; log every qualified conversation to the tracker same-day. |
| 10 | Gate skipped under deadline | Post ships without sign-off | No gate, no advance. A missed slot is recoverable; an off-brand or unverified post is not. |
| 11 | Backlog runs dry | Monday has no approved ideas | Keep ≥2 weeks of approved briefs in backlog. Ideation is part of weekly review. |

---

## 18. Definition of done

A carousel is **done** only when **all** of the following are true:

- [ ] Maps to a topic cluster, a framework, a buyer pain, and a single CTA.
- [ ] Every public statistic used is **Tier 1 evidence**, sourced and linked.
- [ ] Passed all four gates (G1 brief, G2 evidence, G3 copy, G4 final), each logged with approver + date.
- [ ] Uses AJ Digital language and contains **no public-facing agent/automation jargon**.
- [ ] Built on the locked brand kit; legible at thumbnail size.
- [ ] **Published manually by a human** in one of the two fixed weekly slots (V0).
- [ ] Post URL captured; tracker status = Published.
- [ ] 24-hour analytics baseline logged; 7-day analytics scheduled.
- [ ] Any qualified conversation it generates is recorded against it.
- [ ] Reviewed in the weekly review; learnings written down.

A week's production is done when **both** carousels meet the above and next week's two briefs are approved at G1.

The V0 phase is done when **30 days** have run at 2/week and the monthly optimization review has recorded a decision on cadence and the move toward V1.
