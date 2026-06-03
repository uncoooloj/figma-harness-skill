# Example Scenarios

Use these examples to show what a good first response should do before implementation.

## Single Figma Screen To React

Prompt:

```text
Use $figma-harness to implement this Figma screen in the existing React app: <link>
```

Good first response:

- Confirm target repo/framework from local context.
- Inspect the link or ask for exports if inaccessible.
- Create source inventory with one canonical source.
- Ask only if target route, interactions, or missing states are unclear.

## Multiple Conflicting Links

Prompt:

```text
Use $figma-harness. Here are two signup flow links and a component library link.
```

Good first response:

- Classify screen links and component-library link separately.
- Detect whether the flows conflict or represent platform variants.
- Ask which flow is canonical before coding.

## Whole Figma File

Prompt:

```text
Use $figma-harness on this whole Figma file and build the product UI.
```

Good first response:

- Refuse to implement the whole file as one target.
- Map pages/frames into design system, screens, flows, archive, experiment, and unknown.
- Ask which flow or platform is in scope.

## Web And Mobile Variants

Prompt:

```text
Implement the web and mobile designs from these Figma links.
```

Good first response:

- Identify whether web and mobile should share tokens/components only or share runtime code.
- Ask for architecture if cross-platform target is unclear.
- Build a design model with platform-specific screens and shared tokens.

## Screenshot Only

Prompt:

```text
I only have these exported screenshots. Use the harness.
```

Good first response:

- State that component metadata is unavailable.
- Inventory screenshots as lower-confidence sources.
- Ask for missing states or target framework only if needed before coding.
