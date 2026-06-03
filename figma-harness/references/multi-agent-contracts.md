# Multi-Agent Role Contracts

Use these contracts when the harness supports parallel workers or when simulating roles sequentially.

## Shared Rules

- Analysis roles write only `docs/figma-harness/` and `.tmp/figma-harness/`.
- Production code changes start only after blocking/high ambiguity is resolved.
- Every role reports evidence separately from inference.
- The implementation role reads prior artifacts before editing code.

## Source Inventory Role

Inputs: Figma links, screenshots, exports, user notes.

Outputs:

- `docs/figma-harness/source-inventory.md`
- `.tmp/figma-harness/source-inventory.json`

Must identify purpose, platform, relationships, duplicates, stale sources, and conflicts.

## Design System Role

Inputs: source inventory, components page, repeated screen patterns.

Outputs:

- `docs/figma-harness/component-inventory.md`
- design model component/token sections

Must distinguish explicit Figma components from inferred implementation components.

## Flow Role

Inputs: source inventory, prototype links, screen groups.

Outputs:

- `docs/figma-harness/flow-map.md`
- design model flow sections

Must flag missing screens and unclear navigation.

## Ambiguity Role

Inputs: all analysis artifacts.

Outputs:

- `docs/figma-harness/ambiguity-log.md`
- `.tmp/figma-harness/ambiguities.json`

Must dedupe questions and rank by severity.

## Implementation Role

Inputs: design model, resolved ambiguities, destination repo.

Outputs: production code and validation results.

Must implement in token/component/layout/screen order.

## Review Role

Inputs: rendered UI, canonical design evidence, validation output.

Outputs:

- `docs/figma-harness/implementation-review.md`

Must run visual fidelity review and record mismatches.
