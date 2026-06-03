# Interaction And State Inventory

Use this checklist before implementation and during review.

## Common States

| Surface | States to check |
| --- | --- |
| Buttons/links | default, hover, focus, active, disabled, loading |
| Forms | default, focused, validation error, success, submitting, empty |
| Tables/lists | loading, empty, filtered empty, error, pagination, selected row |
| Modals/sheets | open, close, escape/backdrop, destructive confirm |
| Navigation | selected, hover, collapsed, mobile menu, back behavior |
| Cards | default, selected, hover, unavailable, loading media |

## Classification

- Blocking: state affects auth, payment, data loss, permissions, or core task completion.
- High: missing state affects primary workflow quality or accessibility.
- Medium: state can be inferred from existing tokens/components.
- Low: standard browser or platform affordance is acceptable.

## Output

Add missing states to:

- `docs/figma-harness/ambiguity-log.md` when decisions are needed
- `.tmp/figma-harness/design-model.json` under `states`
- `docs/figma-harness/design-to-code-assumptions.md` when inferred
