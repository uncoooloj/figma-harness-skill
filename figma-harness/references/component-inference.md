# Component Inference Heuristics

Use this when the design system is implicit, incomplete, or inconsistent.

## Reuse Threshold

- Appears once: inline may be acceptable.
- Appears twice: candidate component.
- Appears three or more times: reusable component required unless the destination repo has a stronger pattern.

## Component Evidence

Look for:

- repeated visual anatomy
- repeated layout structure
- shared copy positions
- shared interaction states
- Figma components or instances
- detached instances with similar names
- repeated tokens, radii, shadows, or spacing

## Variant Decisions

Normalize when:

- differences look accidental
- screens belong to one current flow
- variants only differ by state or content

Preserve variants when:

- differences map to real state, platform, size, density, or hierarchy
- the component library explicitly defines those variants
- product behavior depends on the distinction

Ask when:

- conflicting variants come from competing source links
- a style difference would shape the public design system
- normalization could hide a product distinction

## Avoid Over-Abstraction

Do not create shared components for:

- one-off hero compositions
- unique marketing art direction
- experimental frames not confirmed as canonical
- patterns that the destination repo already handles differently

## Implementation Target

Map inferred components to the destination repo:

- existing component: extend or add variant
- missing reusable pattern: create component
- page-specific pattern: keep local but document why
