---
name: figma-harness
description: Orchestrate production UI implementation from one or more Figma links, screenshots, or design-file references. Use when an AI coding agent must inspect Figma sources, classify pages/frames/prototypes, resolve ambiguity before coding, infer tokens/components/flows, coordinate web/mobile/cross-platform implementation, and verify rendered UI against the design. Trigger for Figma-to-code, design-to-code, convert Figma to React/Next/Expo/SwiftUI, implement these Figma screens, build from multiple Figma links, or turn a messy Figma file into production UI.
---

# Figma Harness

## Core Intent

Act as a careful product/design engineer before acting as a coding agent. Figma is not a deterministic code spec: files can contain stale screens, duplicate flows, detached instances, partial mobile variants, implicit business logic, and conflicting design-system signals. First inventory and clarify the source of truth; then implement from a confirmed design model.

This skill is a portable harness. It coordinates design intake, ambiguity resolution, design-system inference, implementation, and review for any capable coding agent. It does not replace lower-level Figma, frontend, mobile, or browser-testing skills/tools. When those capabilities are available and relevant, load and follow them as platform adapters.

## Portability Contract

Use the harness as model- and platform-neutral operating instructions. The package is installable as a Codex skill, but the core workflow should also work in Claude Code, Cursor, Gemini CLI, OpenAI Codex CLI, custom MCP harnesses, or any agentic environment with equivalent file, Figma, browser, and code-editing tools.

- Treat platform-specific tool names as adapters, not requirements.
- Preserve the source inventory, ambiguity gate, design model, implementation order, and review gate even when a platform lacks one specific tool.
- If the agent has Figma MCP/API access, inspect designs directly.
- If the agent lacks Figma MCP/API access, ask for frame exports, screenshots, prototype links, design-system docs, or user-selected canonical frames.
- If the agent can run parallel workers, keep analysis writes scoped to docs/tmp artifacts and production writes scoped to the implementation role.
- If the agent cannot run parallel workers, simulate the same roles sequentially.

Adapter examples:

- Codex: install this folder as `figma-harness`; use `agents/openai.yaml` for interface metadata; when calling `use_figma`, load `figma-use` first.
- Claude Code or other coding agents: paste or reference `SKILL.md` as the project instruction/harness; map Figma/browser/test operations to the platform's available tools.
- Custom agent harnesses: implement the workflow states as gates in the orchestrator and persist the same docs/tmp artifacts.

## Operating Mode

Default to `strict_clarification`.

- `strict_clarification`: Resolve blocking and high-impact ambiguity before production code changes. Make only low-risk assumptions and record them.
- `assumption_driven`: Use only when the user explicitly says to make assumptions, use best judgment, move fast, proceed with defaults, decide for them, or not ask questions.

In either mode, avoid vague question loops. Ask the smallest structured batch that unlocks the next phase, usually 3-7 high-impact questions.

## Non-Negotiables

- Inventory every provided design source before implementation.
- Do not assume all links are equally canonical.
- Do not silently choose target platform, framework, routing, navigation, data behavior, auth behavior, payment behavior, or cross-platform architecture.
- Do not implement every frame in a whole Figma file by default. First map the file, identify target surfaces, and confirm what should be built.
- Prefer existing repo patterns, components, styling, state, routing, and testing conventions over generic defaults.
- Build reusable tokens/components/layouts before page-specific screens.
- Do not use image generation, concept redesign, or taste-based reinterpretation to override supplied Figma sources unless the user explicitly asks for a redesign.
- Keep design-analysis artifacts scoped to `docs/figma-harness/` and `.tmp/figma-harness/`.
- Analysis agents may write only scoped docs/tmp artifacts. Only the implementation agent may write production application code.
- If using platform-specific Figma plugin/API tools, load any required tool-specific adapter instructions first.

## Workflow

### 1. Preflight

Identify:

- Design inputs: Figma links, screenshots, prototypes, exported assets, design-system links, component library links, or written specs.
- Target codebase: existing repo, new app, web, mobile, or cross-platform.
- Execution mode: default strict, or explicit assumption-driven.
- Tool access: whether Figma MCP/API, screenshots, browser, simulator, or design exports are available.

If Figma access is blocked, ask for access, screenshots, exports, or specific frames before pretending to inspect the design.

### 2. Source Inventory

Create a source inventory before code changes.

Classify each source by purpose:

- `web_screens`
- `mobile_screens`
- `design_system`
- `component_library`
- `user_flow`
- `prototype`
- `archive`
- `experiment`
- `unknown`

Classify relationships between sources:

- `same_flow`
- `platform_variants`
- `component_library_for_screens`
- `old_and_new_version`
- `duplicate_or_overlap`
- `conflicting`
- `unknown`

Record at minimum:

- URL or source label
- file/page/frame/node if available
- apparent platform
- source purpose
- screens or states represented
- confidence level
- conflicts, duplicates, or missing companion states

Write:

- `docs/figma-harness/source-inventory.md`
- `.tmp/figma-harness/source-inventory.json`

### 3. Ambiguity Gate

Classify ambiguity by severity.

| Severity | Meaning | Action |
| --- | --- | --- |
| `blocking` | Implementation could target the wrong product, platform, source, or architecture | Ask before coding |
| `high` | Wrong choice would cause significant rework or product mismatch | Ask before coding unless assumption-driven |
| `medium` | Choice affects polish, maintainability, or minor behavior | Ask if cheap; otherwise document assumption |
| `low` | Standard implementation detail with reversible impact | Choose a sensible default and document if relevant |

Never silently assume high-impact decisions such as:

- canonical source when links conflict
- web vs mobile vs cross-platform target
- framework, routing, navigation, or app-shell model
- breakpoint strategy when no responsive designs exist
- design-system normalization vs preserving inconsistent variants
- auth, permissions, roles, checkout, payments, persistence, or API behavior
- animation, gesture, keyboard, safe-area, offline/cache, or native platform behavior

Ask structured questions:

```text
Category:
Decision:
Options:
Recommended:
Why it matters:
Consequence if wrong:
```

Update:

- `docs/figma-harness/ambiguity-log.md`
- `.tmp/figma-harness/ambiguities.json`

Proceed only when blocking/high ambiguity is resolved, or when the user explicitly authorizes assumptions.

### 4. Design Model

Build a working design model before implementation.

Write `.tmp/figma-harness/design-model.json` with these sections when relevant:

- `sources`
- `targetPlatform`
- `screens`
- `states`
- `tokens`
- `components`
- `componentVariants`
- `layouts`
- `flows`
- `interactions`
- `responsiveRules`
- `assets`
- `assumptions`
- `unresolvedQuestions`
- `confidence`

Infer the design system from explicit components and repeated visual patterns:

- Appears once: inline may be acceptable.
- Appears twice: candidate component.
- Appears three or more times: reusable component required unless there is a strong repo-specific reason not to.

If component variants conflict, ask whether to normalize them into one canonical component, preserve them as separate variants, or treat one source as stale.

Create conditional docs only when they add clarity:

- `docs/figma-harness/component-inventory.md`
- `docs/figma-harness/web-design-analysis.md`
- `docs/figma-harness/mobile-design-analysis.md`
- `docs/figma-harness/flow-map.md`
- `docs/figma-harness/design-to-code-assumptions.md`

For reusable artifact shapes, load `references/artifact-templates.md`. For the canonical design model structure, load `references/design-model-schema.md`.

### 5. Implementation Plan

Before code changes, state the plan in implementation order:

1. Design tokens
2. Layout primitives
3. Base UI components
4. Composite components
5. Page or screen templates
6. Individual pages/screens
7. Routes or navigation
8. Interaction states
9. Responsive/mobile behavior
10. Tests, Storybook, previews, or examples where applicable

For web, decide or confirm:

- framework and routing model
- styling system
- responsive breakpoints
- SSR/client boundaries where relevant
- accessibility, loading, error, and empty states

For mobile, decide or confirm:

- target framework
- iOS, Android, or both
- navigation model
- safe-area, density, keyboard, gesture, and native-control behavior
- offline/cache and app-state expectations where relevant

For cross-platform work, ask which architecture is intended:

- separate web and mobile codebases
- React Native Web / Expo Router
- shared design tokens only
- shared business logic with separate UI
- design-system generation before screens

### 6. Implementation

Implement from the design model, not frame-by-frame duplication.

- Use existing codebase conventions first.
- Create shared tokens/components before repeated surfaces.
- Preserve visible copy, hierarchy, density, spacing, colors, typography, radii, shadows, icon treatment, and image framing from the canonical design.
- Keep functional UI code-native; do not ship static screenshots as UI.
- Add interactions implied by the design or required by the flow.
- Document intentional deviations as they happen.

For large inputs, use parallel agents only when the harness and user permissions allow it. If parallel agents are unavailable or not permitted, simulate the roles sequentially:

- Source Inventory
- Web Analysis
- Mobile Analysis
- Design System
- Flow Inference
- Ambiguity Resolution
- Implementation
- Review

### 7. Review Gate

Review the rendered implementation against the original design before handoff.

Run available checks:

- lint
- typecheck
- tests
- build
- Storybook or preview checks
- browser/simulator verification

Compare design and implementation at matching viewports or states where possible. Inspect at least:

- source/copy fidelity
- layout and spacing
- typography
- color and elevation
- component variants
- icons and assets
- responsive/mobile behavior
- interactions and state changes

Write `docs/figma-harness/implementation-review.md` with:

- matched sources
- validation commands
- screenshots or viewport evidence when available
- mismatch ledger
- fixed mismatches
- remaining intentional deviations
- unresolved assumptions

Fix material mismatches before final handoff unless blocked by missing design information, missing assets, unavailable tools, or explicit user scope limits.

Functional QA does not replace visual fidelity QA. Passing lint, tests, or build is not enough if the rendered result visibly diverges from the canonical design.

For review artifacts, load `references/visual-qa-ledger.md` and `references/review-rubric.md`. To forward-test whether another agent followed this harness, load `references/forward-test-checklist.md`.

## Whole-File Mode

When given an entire Figma file, do not treat the file as one implementation target. First map pages and frames into:

- design system pages
- component library pages
- web screens
- mobile screens
- prototype flows
- archives/deprecated pages
- experiments
- unknown pages

Then ask which groups or flows are canonical and in scope. Whole-file mode is an intake and source-of-truth mapping phase until the user confirms target surfaces.

## Final Response

Report:

- canonical design sources used
- key decisions confirmed or assumed
- files changed
- validation run
- design-review result
- material deviations or unresolved questions

If implementation did not proceed because strict clarification found blocking ambiguity, lead with the exact questions needed to unblock the next step.
