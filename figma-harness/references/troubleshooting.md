# Troubleshooting

Use this guide when a run drifts away from the harness.

| Symptom | Likely cause | Fix |
| --- | --- | --- |
| Agent starts coding immediately | Source inventory gate was skipped | Stop code changes, inventory sources, and identify blockers |
| Too many questions | Low-risk details are treated as blocking | Batch only blocking/high questions and document low-risk assumptions |
| Wrong flow implemented | Canonicality was assumed | Rebuild source inventory and ask which source is current |
| Components are duplicated per screen | Design-system inference was skipped | Extract repeated tokens/components before continuing |
| Output looks redesigned | Taste-based reinterpretation overrode the source | Restore supplied design as canonical and list deviations |
| Build passes but design is off | Functional QA replaced visual QA | Run mismatch ledger against rendered screenshots |
| Whole file feels overwhelming | File was treated as one target | Switch to whole-file triage and classify pages first |
| Figma access is unavailable | Tool access was assumed | Use no-Figma-access fallback and request exports |

## Recovery Rule

When a high-impact gate was skipped, do not keep layering fixes on top. Pause, reconstruct the missing artifact, then decide whether the existing implementation can be corrected or should be restarted from the confirmed design model.
