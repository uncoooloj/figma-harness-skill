# Flow And Routing

Use this reference to map Figma screens into product navigation before implementation.

## Route Map

Write `docs/figma-harness/flow-map.md` with:

```md
# Flow Map

| Screen ID | Source | Route/screen | Entry point | Next actions | Missing states |
| --- | --- | --- | --- | --- | --- |
| SCR1 | S1 Signup | /signup | nav CTA | submit -> SCR2 | error, loading |
```

## Web Routing

Decide or confirm:

- URL path
- nested layout or app shell
- modal route versus inline state
- redirect behavior
- deep-link behavior
- authenticated versus public route

## Mobile Navigation

Decide or confirm:

- stack, tab, drawer, modal, or sheet
- back behavior
- safe-area behavior
- gesture expectations
- platform-specific differences

## Missing Navigation

Ask before coding when:

- a primary button has no visible destination
- prototype links conflict with screen order
- desktop and mobile show different navigation models
- a modal might be a route on web but a sheet on mobile

Document inferred navigation when the user authorizes assumptions.
