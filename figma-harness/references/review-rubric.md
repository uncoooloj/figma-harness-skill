# Production-Readiness Review Rubric

Use this rubric before final handoff or before opening a code PR from a Figma implementation task.

| Dimension | Weight | Pass bar |
| --- | ---: | --- |
| Source fidelity | 25 | Canonical design sources, layout, copy, typography, color, assets, and density are visibly preserved |
| Component architecture | 20 | Repeated patterns become reusable components or explicit variants, not page-specific duplication |
| Interaction completeness | 15 | Primary states, navigation, forms, empty/loading/error states, and implied interactions work |
| Responsive/platform behavior | 15 | Web/mobile/cross-platform behavior matches supplied designs or documented decisions |
| Accessibility and semantics | 10 | Semantic structure, focus states, labels, contrast, and keyboard behavior are reasonable |
| Validation evidence | 15 | Build/lint/test plus rendered visual review are recorded |

## Verdicts

- `ship`: No blocking/high issues remain.
- `iterate`: Medium issues remain but core design and behavior are correct.
- `block`: Blocking/high design, architecture, or interaction issues remain.

## Review Questions

- Did implementation start from confirmed canonical sources?
- Are tokens/components reused consistently?
- Does the rendered screen match the design at the checked viewport?
- Are any deviations intentional and documented?
- Would a reviewer understand what was verified without replaying the whole session?
