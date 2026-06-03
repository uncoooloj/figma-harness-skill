# Handoff And PR Template

Use this for final responses or GitHub PR descriptions after implementing from Figma.

## Final Response

```md
Implemented the confirmed Figma scope.

Design sources:
- Canonical:
- Ignored/stale:

Key decisions:
- Confirmed:
- Assumed:

Changed files:
- <path>

Validation:
- <command/result>
- Rendered review:

Visual review:
- Viewports/states checked:
- Remaining deviations:

Unresolved:
- <question/risk if any>
```

## GitHub PR Body

```md
## Summary
- Implements <screen/flow/component> from the confirmed Figma source
- Adds/updates shared components before page-specific UI
- Documents assumptions and visual review evidence

## Design Sources
- Canonical: <source IDs/links>
- Out of scope: <source IDs/links>

## Decisions
- <confirmed decision>
- <assumption and why>

## Validation
- <lint/typecheck/test/build>
- <browser/simulator/storybook review>

## Visual QA
- <viewport/state checked>
- <mismatches fixed>
- <remaining intentional deviations>

## Issues
Closes #<number>
```
