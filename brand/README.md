# Audio Jones Brand System

This directory is the canonical source for Audio Jones / AJ Digital brand meaning, messaging, visual direction, and machine-readable marketing constraints.

## Authority model

- **Canonical meaning and rules:** `AudioJones-Dev/audiojonesops/brand`
- **Visual asset library:** `AudioJones-Dev/AudioJonesBranding`
- **Generated outputs:** downstream artifacts compiled from approved files in this directory
- **Production tools:** Canva, Figma, image generators, websites, and campaign repositories consume this system; they do not redefine it

> Meaning lives in `audiojonesops`. Media lives in `AudioJonesBranding`. Applications consume both.

## Source hierarchy

1. `BRAND_SPINE.md` — durable brand doctrine requiring explicit owner approval to change.
2. `brand.schema.yaml` — machine-readable brand source used by automation.
3. `visual/style-os.yaml` — visual marketing and wardrobe-generation rules.
4. `schemas/visual-scene.schema.json` — validation contract for generated visual briefs.
5. Campaign overlays — bounded adaptations that may not contradict the Brand Spine.
6. Generated files — compiled artifacts; never edited manually.

## Current status

The system is **draft / validation phase**. It is structured for automation but is not considered locked until unresolved brand tokens are completed, the visual system is tested against a reference dataset, governance checks are implemented, and Audio Jones explicitly approves a versioned lock file.

## Operating rule

All material brand changes occur on a feature branch and enter `main` through an approved pull request. Merging to `main` makes the change canonical.