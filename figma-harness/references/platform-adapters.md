# Platform Adapters

The harness is platform-neutral. Use this guide to map workflow stages to a specific agent environment.

## Codex

- Install as `~/.codex/skills/figma-harness`.
- Use `agents/openai.yaml` for interface metadata.
- Load required Figma skills before Figma MCP/API calls.
- Use local git for branches/commits and GitHub tools for issues/PRs.
- Use browser/simulator tools when rendered UI needs verification.

## Claude Code

- Paste or reference `figma-harness/SKILL.md` as project instructions.
- Map file edits to Claude Code's workspace tools.
- Use available MCP Figma/browser tools if configured.
- If no Figma MCP is available, use the no-access fallback and request exports.

## Cursor Or IDE Agents

- Keep `SKILL.md` in the repo or prompt context.
- Ask the agent to write docs/tmp artifacts before production edits.
- Use the IDE's terminal/test/browser affordances for validation.
- Keep review evidence in `docs/figma-harness/`.

## Custom MCP Harnesses

- Implement gates as orchestrator states: preflight, inventory, ambiguity, design model, implementation, review.
- Persist `.tmp/figma-harness/design-model.json` between agent calls.
- Give analysis workers docs/tmp write access only.
- Give production code write access only after blocking/high ambiguity is resolved.

## Minimal Tool Mapping

| Harness need | Any-platform equivalent |
| --- | --- |
| Figma inspection | Figma MCP/API, exports, screenshots, prototype captures |
| Code edits | repo file-editing tool |
| Render verification | browser, simulator, Storybook, screenshot capture |
| Validation | lint, typecheck, test, build |
| Review | side-by-side evidence and mismatch ledger |
