# Accessibility Mapping

Use this to map visual design into accessible implementation work.

## Checklist

- semantic heading structure
- button/link semantics
- labels for inputs and icon buttons
- keyboard focus order
- visible focus states
- contrast for text, controls, and states
- reduced-motion behavior for animations
- error messaging connected to inputs
- aria attributes only where native semantics are insufficient
- mobile safe areas and touch target sizes

## Ask When

Ask before coding when:

- accessibility behavior changes product behavior
- motion is central but reduced-motion alternative is unclear
- visual-only affordances hide required information
- platform-specific native accessibility expectations are unknown

## Assume When

Assume standard accessible defaults when they do not change product behavior:

- semantic HTML for web
- labels for form controls
- focus states matching existing tokens
- keyboard operation for menus and dialogs

Record accessibility assumptions in the implementation review.
