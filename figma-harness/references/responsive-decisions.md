# Responsive Decisions

Use this when responsive behavior is missing, partial, or split across multiple Figma links.

## Inputs

- desktop frames
- tablet/mobile frames
- platform-specific links
- existing repo breakpoints
- product requirements

## Decision Matrix

| Design evidence | Action |
| --- | --- |
| Desktop and mobile frames exist | Implement both and map shared/different components |
| Desktop only, mobile required | Ask whether to infer or wait |
| Desktop only, desktop-only scope | Document scope and avoid inventing mobile UI |
| Multiple mobile variants conflict | Ask which is canonical |
| Existing repo has breakpoints | Prefer repo breakpoints unless design requires otherwise |

## Document

- breakpoint names and pixel values
- layout changes by breakpoint
- nav changes by breakpoint
- content hidden, reordered, or transformed
- assumptions and confidence

## Blocking Questions

Ask before coding when:

- mobile fidelity matters but no mobile design exists
- desktop and mobile show different information architecture
- cross-platform architecture is unclear
