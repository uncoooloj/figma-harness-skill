# Install And Portability Notes

This repository has two layers:

1. Portable harness instructions in `figma-harness/SKILL.md`
2. Codex-specific skill packaging in `figma-harness/agents/openai.yaml`

## Codex

```bash
mkdir -p ~/.codex/skills
cp -R figma-harness ~/.codex/skills/figma-harness
```

Invoke with:

```text
Use $figma-harness to turn these Figma links into production UI code.
```

## Other Agents

Use `figma-harness/SKILL.md` as the operating manual. If the platform supports project rules, paste or link the skill there. If it supports slash commands or prompt libraries, wrap the invocation around the same workflow.

## What Must Stay Portable

- source inventory
- ambiguity gate
- design model
- implementation order
- review gate

## What Can Be Adapter-Specific

- how Figma is inspected
- how files are edited
- how browsers or simulators are launched
- how validation commands are run
- how multi-agent workers are spawned
