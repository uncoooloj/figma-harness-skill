# Visual Clarification

Use screenshots or crops when a clarification question depends on a specific visual region. A good visual question should let the user answer without reopening the whole Figma file.

## When To Include Visual Evidence

Include visual evidence for:

- conflicting versions of the same screen
- component variant differences
- unclear navigation destinations
- missing or ambiguous responsive behavior
- visual inconsistencies that may be stale work
- implementation review mismatches

Do not include screenshots when the question is purely architectural, such as framework choice, repo target, or API ownership.

## Question Shape

```text
Category:
Decision:
Visual evidence:
  - Source: S1 / frame name / viewport
  - Screenshot: <attachment, local path, or URL>
  - Callout: Region A shows the conflicting button radius
Options:
Recommended:
Why it matters:
Consequence if wrong:
```

## Capture Choice

- Use a full-frame screenshot when the decision depends on screen context.
- Use a crop when the decision is about one component, state, or small region.
- Use side-by-side screenshots when asking which source is canonical.
- Use rendered implementation screenshots when asking about design drift after coding.

## Annotation Conventions

If annotation tools are available:

- mark regions as `A`, `B`, `C`
- keep labels outside important UI content when possible
- use one callout per decision
- avoid decorative markup that hides the design

If annotation tools are unavailable, describe the region precisely:

```text
Visual evidence: S2 / Pricing page / top-right primary CTA. The button labeled "Start" uses a 12px radius, while S1 uses 8px.
```

## Output Rule

Return visual evidence in the user-visible clarification message when the platform supports it. Also record each image in the screenshot manifest so later review can trace the question back to the source.
