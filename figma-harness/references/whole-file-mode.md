# Whole-File Mode

Whole-file mode is an intake phase, not permission to implement every frame.

## Process

1. Map pages and sections.
2. Classify frames by purpose.
3. Identify duplicates, archives, experiments, and stale versions.
4. Detect design-system pages and component libraries.
5. Group frames into likely flows.
6. Ask which groups are canonical and in scope.
7. Only then build a design model for the selected surfaces.

## Page Categories

- `design_system`
- `component_library`
- `web_screens`
- `mobile_screens`
- `prototype_flows`
- `archive`
- `experiment`
- `unknown`

## Frame Signals

| Signal | Meaning | Action |
| --- | --- | --- |
| Page named Archive, Old, V1, Exploration | likely stale | Do not implement without confirmation |
| Multiple similar flows | canonical conflict | Ask which is current |
| Components page with variants | design-system source | Use for tokens/components |
| Prototype links between frames | flow evidence | Add to flow map |
| Desktop but no mobile | responsive ambiguity | Ask or document assumption |

## Output

Write `docs/figma-harness/source-inventory.md` with:

- page map
- frame groups
- likely canonical sources
- stale/unknown sources
- conflicts
- questions needed to choose scope
