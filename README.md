# figma-harness-skill

A Codex skill for turning messy Figma inputs into production UI through a disciplined harness: source inventory, ambiguity resolution, design-system inference, implementation order, and rendered review.

## Install

Copy the installable skill folder into your Codex skills directory:

```bash
mkdir -p ~/.codex/skills
cp -R figma-harness ~/.codex/skills/figma-harness
```

Then invoke it with:

```text
Use $figma-harness to turn these Figma links into production UI code.
```

## Package Shape

- Repository: `figma-harness-skill`
- Skill folder: `figma-harness`
- Skill name: `figma-harness`

The skill folder is intentionally clean: `SKILL.md` plus Codex interface metadata in `agents/openai.yaml`.
