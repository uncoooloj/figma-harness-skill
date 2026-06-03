# No-Figma-Access Fallback

Use this when Figma links are present but the agent cannot inspect the file directly.

## Do Not Pretend

Do not claim to inspect frames, components, variants, or styles that are inaccessible. State the access blocker and ask for the smallest useful substitute.

## Acceptable Substitutes

- exported PNG/JPG screenshots at target viewport sizes
- selected frame exports for each canonical screen/state
- prototype links plus screenshots of each step
- design-system docs or token exports
- component-library screenshots
- user-selected canonical frame names
- existing implementation screenshots if the task is matching or migration

## Minimum Request

Ask for:

1. canonical screen/frame exports
2. target platform and framework
3. any mobile/responsive variants
4. important interaction states
5. known stale or experimental links to ignore

## Fallback Inventory

When only screenshots are available, still create a source inventory:

| ID | Source | Type | Platform | State | Confidence | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| S1 | signup-desktop.png | screenshot | web | default | medium | No component metadata |

## Implementation Rule

Treat screenshot-only work as lower confidence. Use visual inference for tokens/components, but do not invent product behavior that the screenshot does not show.
