# Brand-to-Marketing Automation Roadmap

## Objective

Turn the approved Audio Jones / AJ Digital brand system into a deterministic control layer for marketing operations, visual generation, content production, and downstream publishing.

## Phase 1 — Canonical foundation

- Approve `brand/BRAND_SPINE.md`.
- Resolve palette and typography tokens.
- Validate `brand/brand.schema.yaml` and `brand/visual/style-os.yaml`.
- Add campaign overlays for Audio Jones, AJ Digital, Eightee20 Society, and Florida Ramp & Lift.
- Define source-to-generated compilation rules.

**Exit gate:** brand status moves from `draft` to `candidate`.

## Phase 2 — Validation dataset

Build a 50-outfit reference dataset:

- 10 high-reliability looks;
- 10 medium-reliability edge cases;
- 10 explicit failures;
- 10 South Florida operator looks;
- 10 occupation-specific looks.

Each record must capture garments, numeric attributes, formality distance, bridge mechanisms, reliability score, context, climate, body-fit notes, failure risks, safer alternative, and expressive alternative.

**Exit gate:** scoring weights are calibrated against reviewed examples.

## Phase 3 — Compiler and CI

Implement commands equivalent to:

- `brand:validate`
- `brand:lint-language`
- `brand:validate-tokens`
- `brand:validate-style`
- `brand:compile`
- `brand:check-generated`

CI must reject invalid YAML or JSON, unresolved production tokens, prohibited public vocabulary, campaign overlays that conflict with the Brand Spine, non-high-reliability visual scenes without bridge logic, and stale generated artifacts.

**Exit gate:** every brand PR receives deterministic checks.

## Phase 4 — Lock and release

Generate a versioned `brand.lock.yaml` containing brand version, schema version, source paths, commit SHA, source hash, generated artifact paths, approval state, approver, and approval timestamp.

**Exit gate:** status becomes `locked`.

## Phase 5 — Visual generation workflow

1. Campaign request
2. Brand context resolution
3. Campaign and channel overlay
4. Style OS outfit resolution
5. Visual-scene compilation
6. Prompt compilation
7. Image generation
8. Machine validation
9. Human approval
10. Asset registration in `AudioJonesBranding`
11. Publishing handoff

Required asset states: `generated`, `machine_validated`, `review_required`, `approved`, `rejected`, `superseded`, and `published`.

## Phase 6 — Marketing operations integration

Use the locked brand context to govern website copy and imagery, LinkedIn and Instagram content, carousel production, podcast and video thumbnails, campaign briefs, deck visuals, email campaign voice, Eightee20 Society identity, and client-specific visual overlays.

## Immediate next work items

1. Resolve canonical color values and body font.
2. Import the Modern Menswear Style Matrix under `brand/visual/`.
3. Create the 50-look dataset schema and seed records.
4. Add JSON Schema validation for the root brand object and outfit records.
5. Add campaign overlay schemas.
6. Build a compiler that produces `brand-context.json` and an image-system prompt.
7. Add a generated asset manifest contract for `AudioJonesBranding`.
