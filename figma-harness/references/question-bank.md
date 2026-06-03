# Clarification Question Bank

Ask only questions that unlock the next phase. Use this shape:

```text
Category:
Decision:
Options:
Recommended:
Why it matters:
Consequence if wrong:
```

## Conflicting Sources

```text
Category: Source of truth
Decision: I found two signup flows with different step order. Which is canonical?
Options: A. Phone-first flow, B. Email-first flow, C. Neither; wait for a new link
Recommended: A if it is the launch-ready page; C if both are exploratory
Why it matters: This determines routes, form state, validation, and analytics events.
Consequence if wrong: The implementation could ship the wrong signup experience.
```

## Missing Mobile Design

```text
Category: Responsive behavior
Decision: No mobile design was provided. How should I handle mobile?
Options: A. Wait for mobile Figma links, B. Infer mobile from desktop, C. Implement desktop only
Recommended: A if mobile fidelity matters; B if speed matters
Why it matters: Navigation, layout, spacing, and interaction patterns may change on mobile.
Consequence if wrong: The app may need a responsive rewrite.
```

## Component Variant Conflict

```text
Category: Design system
Decision: Primary buttons appear with 8px, 10px, and 12px radii. Should I normalize them?
Options: A. Normalize to one Button component, B. Preserve as variants, C. Treat one source as stale
Recommended: A if all screens are one product surface; C if sources are different versions
Why it matters: This controls component architecture and visual consistency.
Consequence if wrong: The codebase may encode accidental Figma drift as real variants.
```

## Unknown Framework

```text
Category: Implementation target
Decision: Which framework should receive this UI?
Options: A. Existing repo framework, B. React/Next, C. Expo/React Native, D. Other specified target
Recommended: A when an existing codebase is present
Why it matters: Routing, styling, components, tests, and build checks depend on the target.
Consequence if wrong: The output may be unusable in the destination app.
```

## Missing Interaction States

```text
Category: Interaction states
Decision: The design shows default form fields but not error, loading, or success states. How should I proceed?
Options: A. Ask for missing states, B. Infer standard states from design tokens, C. Implement default only
Recommended: B for low-risk forms; A for checkout, auth, or regulated flows
Why it matters: State design affects validation, accessibility, and product behavior.
Consequence if wrong: Critical states may feel bolted on or behave incorrectly.
```

## Data/Auth/Payment Behavior

```text
Category: Product behavior
Decision: The UI implies gated content, but no auth or permission rules are specified. What should drive access?
Options: A. Existing app auth model, B. Placeholder local state, C. Wait for product rules
Recommended: C when access controls affect real users or payments
Why it matters: Auth and payment assumptions are high-impact product decisions.
Consequence if wrong: The implementation can create security, data, or business logic defects.
```
