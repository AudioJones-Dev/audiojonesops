# Brand System Change Policy

## Purpose

Protect the Audio Jones / AJ Digital brand system from drift while allowing controlled iteration and campaign adaptation.

## Change classes

### Major

Includes changes to category positioning, target audience, brand promise, strategic beliefs, visual identity thesis, prohibited positioning, or canonical repository authority.

**Required approval:** Audio Jones.

### Minor

Includes new campaign archetypes, approved vocabulary, channel rules, visual tokens, scoring-model adjustments, or schema extensions that do not contradict the Brand Spine.

**Required approval:** Audio Jones or an explicitly delegated brand-system reviewer.

### Patch

Includes typo corrections, formatting, examples, non-semantic metadata, and documentation clarifications.

**Required approval:** delegated reviewer permitted.

## Workflow

1. Create a feature branch.
2. Change source files only.
3. Validate YAML and JSON syntax.
4. Validate references and prohibited terms.
5. Compile generated artifacts.
6. Confirm generated artifacts match source.
7. Open a pull request describing semantic impact.
8. Obtain required approval.
9. Merge to `main`.
10. Tag or lock approved releases when the system reaches release status.

## Lock states

- `draft` — incomplete and expected to change.
- `candidate` — structurally complete and undergoing validation.
- `locked` — approved for production workflows.
- `superseded` — retained for traceability but no longer active.

## Automation constraints

- Generated files must never be edited manually.
- Campaign overlays may narrow or emphasize the brand but may not contradict the Brand Spine.
- Unresolved tokens must fail production compilation.
- Medium, advanced, or low-reliability wardrobe pairings must include explicit bridge logic.
- Public factual claims require evidence metadata.
- Generated marketing assets require human approval before publication.

## Cross-repository rule

`AudioJonesBranding` stores assets and may receive generated manifests or token exports. It must not maintain independent canonical copies of positioning, voice, Style OS logic, or brand governance.