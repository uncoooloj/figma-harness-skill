# Screenshot Evidence

Use screenshot evidence to make clarification and review auditable.

## Manifest

Write `docs/figma-harness/screenshot-manifest.md` when screenshots or crops affect decisions.

```md
# Screenshot Manifest

| ID | Kind | Source ID | Frame/state | Viewport | Path or URL | Related question | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| IMG1 | source-crop | S1 | Signup / default | 1440x900 | docs/figma-harness/images/img1.png | A1 | Button radius conflict |
```

## Kinds

- `source-frame`: full Figma frame or exported design screen
- `source-crop`: cropped region from source design
- `component`: component or variant evidence
- `prototype-state`: state reached through a prototype
- `rendered-page`: implementation screenshot
- `rendered-crop`: cropped implementation region
- `comparison`: side-by-side or annotated comparison

## Naming

Use stable, boring names:

```text
docs/figma-harness/images/S1-signup-default-1440.png
docs/figma-harness/images/A3-button-radius-comparison.png
```

## Capture Rules

- Capture the smallest image that explains the decision.
- Record source ID, frame name, state, and viewport.
- Prefer canonical source screenshots over inferred screenshots.
- Keep rendered screenshots tied to the exact implementation state being reviewed.
- Do not store large image dumps when a manifest row and one crop is enough.

## Fallback

If images cannot be attached or stored, include a text-only visual reference:

```text
Screenshot unavailable. Visual reference: S1 / Header / desktop frame / nav item group at x=840-1120.
```
