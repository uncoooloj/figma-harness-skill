# Data And Content Mapping

Use this when Figma implies data behavior that is not explicitly specified.

## Mapping Table

```md
# Data And Content Map

| UI element | Source | Data/source assumption | Behavior | Risk | Decision |
| --- | --- | --- | --- | --- | --- |
| Email field | S1 Signup | user.email | required, validated | high | ask |
| Activity table | S3 Dashboard | existing API unknown | sortable/filterable | medium | infer if demo |
```

## High-Risk Assumptions

Ask before coding when UI implies:

- authentication or permissions
- payment or billing
- user roles
- personally identifiable data
- external API writes
- destructive actions
- regulated or financial data

## Lower-Risk Assumptions

Document and proceed when:

- demo seed data is enough
- copy can come from visible Figma text
- table sorting/filtering is visual-only in scope
- existing repo already defines the data contract

## Content Rules

- Preserve visible copy from canonical designs.
- Do not invent product claims or labels.
- If repeated content looks like sample data, use realistic but clearly local seed data.
- Keep content changes listed in the final handoff.
