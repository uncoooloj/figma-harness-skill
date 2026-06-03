# figma-harness-skill

A portable agent harness for turning messy Figma inputs into production UI through source inventory, ambiguity resolution, design-system inference, implementation order, and rendered review.

This repo is packaged as an installable Codex skill, but the core `SKILL.md` is intended to work as model- and platform-neutral operating instructions for any capable coding agent.

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

Use `figma-harness/SKILL.md` as the operating manual in Claude Code, Cursor, Gemini CLI, custom MCP runners, or other agentic coding environments. Map the Figma, browser, code-editing, and validation steps to the tools available in that platform.

## Package Shape

- Repository: `figma-harness-skill`
- Skill folder: `figma-harness`
- Skill name: `figma-harness`

The skill folder is intentionally clean: portable instructions in `SKILL.md` plus Codex interface metadata in `agents/openai.yaml`.
