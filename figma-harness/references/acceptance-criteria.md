# Acceptance Criteria

Use this template after blocking/high ambiguity is resolved and before production code changes.

```md
# Acceptance Criteria

## Sources
- Canonical sources:
- Ignored/stale sources:
- Confirmed assumptions:

## Screens And Routes
- [ ] SCR1 maps to `/signup`
- [ ] SCR2 maps to `/signup/verify`

## Components
- [ ] Shared Button supports primary/secondary/loading/disabled
- [ ] FormField supports label/error/helper text

## States
- [ ] Default state
- [ ] Loading state
- [ ] Error state
- [ ] Empty state where applicable

## Responsive/Platform
- [ ] Desktop matches source viewport
- [ ] Mobile behavior is confirmed or documented

## Validation
- [ ] lint/typecheck/build run where available
- [ ] rendered UI compared against canonical design
- [ ] mismatch ledger has no unresolved blocking/high items
```

Acceptance criteria should reference source IDs and ambiguity IDs when they matter.
