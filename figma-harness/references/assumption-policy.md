# Assumption Policy Examples

Use this reference to decide what can be assumed and what must be asked.

## Blocking

Ask before coding:

- Which of two conflicting flows is canonical
- Whether the target is web, mobile, or cross-platform
- Which repo or framework should receive the UI
- Whether an archive page is still in scope
- Real auth, role, payment, or permission behavior

## High

Ask before coding unless the user explicitly authorizes assumptions:

- Mobile behavior when no mobile design exists
- Navigation model for multi-screen flows
- Whether inconsistent variants should be normalized
- API/data model implied by forms, tables, checkout, or dashboards
- Animation or gesture behavior central to the experience

## Medium

Ask if cheap; otherwise assume and document:

- Empty/loading/error states for low-risk surfaces
- Minor responsive wrapping details
- Hover/focus treatment derived from existing tokens
- Placeholder local state for demo-only controls

## Low

Assume sensible defaults:

- Semantic HTML where applicable
- Accessible labels for icon buttons
- Keyboard focus states
- Minor spacing approximation when exact values are unavailable
- Naming conventions that follow the destination repo

## Assumption-Driven Mode

When the user says to move fast or use best judgment:

- still inventory sources
- still document high-impact assumptions
- prefer reversible implementation choices
- state the riskiest assumptions in the final response
