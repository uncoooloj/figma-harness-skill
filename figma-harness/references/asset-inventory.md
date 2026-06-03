# Asset Inventory

Use this to track images, icons, logos, product renders, avatars, illustrations, and background media.

## Inventory

```md
# Asset Inventory

| ID | Source | Type | Usage | Required fidelity | Handling | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| ASSET1 | S1 Hero | image | hero background | high | export from Figma | crop must match source |
```

## Handling Options

- export from Figma
- reuse existing repo asset
- use icon library component
- request source asset
- generate only if the user asks for creative/redesign work
- use temporary placeholder only if documented and acceptable

## Rules

- Do not replace supplied brand/product assets with generic placeholders.
- Do not use image generation to override supplied Figma assets unless the user asks for redesign or asset creation.
- Keep UI text code-native unless it is part of a real image asset.
- Record missing or low-fidelity assets as review risks.

## Public Repo Safety

Do not commit private or licensed assets unless the user confirms they are safe to publish.
