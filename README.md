# figma-harness-skill

Figma-to-code usually fails in the same quiet way: the agent treats the design file like a finished specification.

But a real Figma file is rarely that clean. It can contain old flows, experimental frames, detached components, duplicated screens, partial mobile states, inconsistent variants, and design-system clues that are implied rather than documented. If an agent starts coding from the first frame it sees, the result is often a brittle pile of page-specific UI that looks plausible for one screenshot and falls apart as soon as the product needs to behave like software.

`figma-harness` is a portable operating manual for avoiding that failure mode.

It teaches a coding agent to slow down at the right moments: inventory the design sources, decide which screens are canonical, identify ambiguity, infer the design system, confirm the implementation plan, then build reusable production UI and verify the result against the original design.

## What It Does

The harness turns Figma-to-code into a staged workflow:

1. Inspect every supplied Figma link, screenshot, prototype, or design-system reference.
2. Classify sources as screens, flows, component libraries, design systems, archives, experiments, or unknowns.
3. Ask structured questions for decisions that would cause expensive rework if guessed.
4. Build a working design model with sources, screens, tokens, components, flows, assumptions, and unresolved questions.
5. Implement in the right order: tokens, primitives, components, layouts, screens, routes, interactions, and responsive behavior.
6. Review rendered UI against the canonical design, not just against lint or build output.

The goal is not to make an agent timid. The goal is to make it product-aware enough to avoid confidently building the wrong thing.

## When To Use It

Use `figma-harness` when you want an AI coding agent to implement production UI from:

- one or more Figma links
- a messy whole Figma file
- desktop and mobile variants
- design-system or component-library references
- prototypes or user flows
- screenshots or exported frames
- a mix of old and new design sources

It is especially useful when the design input is ambiguous, large, multi-platform, or likely to contain stale work.

## What Makes It Different

Most design-to-code prompts optimize for speed: "here is a design, generate the UI."

This harness optimizes for correctness before speed. It asks the agent to behave like a design-systems-aware frontend engineer:

- find the source of truth before coding
- distinguish blocking ambiguity from harmless implementation details
- reuse or infer components instead of duplicating every frame
- preserve supplied designs rather than redesigning them
- support web, mobile, and cross-platform targets explicitly
- document assumptions and review mismatches

## Model And Platform Neutral

This repo is packaged as an installable Codex skill, but the core `SKILL.md` is intentionally model- and platform-neutral.

You can use it as an operating manual in:

- Codex
- Claude Code
- Cursor
- Gemini CLI
- OpenAI Codex CLI
- custom MCP or multi-agent harnesses
- any coding-agent environment with equivalent file, Figma, browser, and validation tools

Platform-specific tool names are treated as adapters. The important part is the workflow: source inventory, ambiguity gate, design model, implementation order, and rendered review.

## Codex Install

Copy the installable skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R figma-harness ~/.codex/skills/figma-harness
```

Then invoke it with:

```text
Use $figma-harness to turn these Figma links into production UI code.
```

## Other Agent Harnesses

Use [`figma-harness/SKILL.md`](figma-harness/SKILL.md) as the operating manual in your agent environment. Map the Figma, browser, code-editing, and validation steps to the tools available in that platform.

For example:

- In Claude Code, paste or reference the skill instructions before handing over Figma links.
- In a custom MCP harness, implement the workflow stages as explicit gates.
- In an agent team, keep analysis agents scoped to docs/tmp artifacts and reserve production code writes for the implementation role.

## Package Shape

- Repository: `figma-harness-skill`
- Skill folder: `figma-harness`
- Skill name: `figma-harness`

The skill folder is intentionally clean: portable instructions in `SKILL.md` plus Codex interface metadata in `agents/openai.yaml`.
