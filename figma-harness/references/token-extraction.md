# Token Extraction

Use this when the design system is explicit, partial, or inferred.

## Token Groups

- colors
- typography
- spacing
- radii
- borders
- shadows/elevation
- motion timing

## Primitive Versus Semantic

Primitive tokens describe raw values:

```text
color.gray.900 = #111827
space.4 = 16px
radius.md = 8px
```

Semantic tokens describe intent:

```text
color.background.default
color.text.muted
color.action.primary
```

Prefer semantic tokens in components when the destination repo supports them.

## Extraction Rules

- Use existing repo tokens first.
- Treat Figma variables/styles as stronger evidence than sampled pixels.
- Normalize near-identical values when they appear accidental.
- Preserve distinct values when they map to real variants or hierarchy.
- Record low-confidence inferred tokens in assumptions.

## Output

Add token decisions to:

- `.tmp/figma-harness/design-model.json`
- `docs/figma-harness/component-inventory.md`
- destination repo token/theme files when implementation begins
