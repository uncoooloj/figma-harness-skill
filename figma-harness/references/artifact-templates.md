# Artifact Templates

Use these templates when the harness asks for docs or temporary artifacts. Keep artifacts concise, source-backed, and easy to resume.

## `docs/figma-harness/source-inventory.md`

```md
# Source Inventory

## Summary
- Target:
- Mode: strict_clarification | assumption_driven
- Figma/API access:
- Canonical source status: confirmed | unresolved | assumed

## Sources
| ID | Source | Purpose | Platform | Frames/states | Confidence | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| S1 | <url/label> | web_screens | web | <frames> | high | <notes> |

## Relationships
| Sources | Relationship | Evidence | Action |
| --- | --- | --- | --- |
| S1/S2 | old_and_new_version | <evidence> | Ask which is canonical |

## Conflicts
- <conflict and affected implementation choice>
```

## `docs/figma-harness/ambiguity-log.md`

```md
# Ambiguity Log

| ID | Severity | Category | Decision | Options | Recommended | Status |
| --- | --- | --- | --- | --- | --- | --- |
| A1 | blocking | canonicality | Which signup flow is current? | A/B | A if latest launch | unresolved |

## Questions To Ask
1. Category:
   Decision:
   Options:
   Recommended:
   Why it matters:
   Consequence if wrong:

## Resolved Answers
- A1:
```

## `docs/figma-harness/design-to-code-assumptions.md`

```md
# Assumptions

| ID | Severity | Assumption | Reason | Validation path | Reversible? |
| --- | --- | --- | --- | --- | --- |
| AS1 | low | Add focus states matching button color | Accessibility default | Browser QA | yes |
```

## `docs/figma-harness/implementation-review.md`

```md
# Implementation Review

## Sources Checked
- Canonical source:
- Viewports/states:
- Screenshots or captures:

## Validation
| Check | Command/tool | Result | Notes |
| --- | --- | --- | --- |
| Skill validation | <command> | pass | |

## Mismatch Ledger
| ID | Severity | Design evidence | Render evidence | Fix | Status |
| --- | --- | --- | --- | --- | --- |
| M1 | high | Button radius 8px | Render 12px | Updated token | fixed |

## Remaining Deviations
- <intentional or blocked deviation>
```

## `.tmp/figma-harness/design-model.json`

Use `references/design-model-schema.md` for the canonical shape.
