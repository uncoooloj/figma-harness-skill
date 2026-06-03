# Design Model Schema

Persist the working model at `.tmp/figma-harness/design-model.json`. Keep it valid JSON and update it when the source of truth changes.

```json
{
  "version": 1,
  "mode": "strict_clarification",
  "targetPlatform": {
    "kind": "web",
    "framework": "unknown",
    "confidence": "medium"
  },
  "sources": [
    {
      "id": "S1",
      "label": "Signup flow",
      "url": "https://figma.com/...",
      "purpose": "web_screens",
      "platform": "web",
      "page": "Launch",
      "frames": ["Signup", "Verify phone"],
      "confidence": "high",
      "canonical": true,
      "notes": []
    }
  ],
  "relationships": [
    {
      "sourceIds": ["S1", "S2"],
      "type": "old_and_new_version",
      "evidence": "Different signup order",
      "resolution": "S1 confirmed canonical"
    }
  ],
  "screens": [
    {
      "id": "SCR1",
      "name": "Signup",
      "sourceId": "S1",
      "routeOrScreen": "/signup",
      "states": ["default", "error"],
      "confidence": "high"
    }
  ],
  "tokens": {
    "colors": [],
    "typography": [],
    "spacing": [],
    "radii": [],
    "shadows": []
  },
  "components": [
    {
      "id": "C1",
      "name": "Button",
      "evidence": ["Appears in SCR1", "Appears in SCR2"],
      "variants": ["primary", "secondary"],
      "implementationTarget": "shared component",
      "confidence": "high"
    }
  ],
  "flows": [
    {
      "id": "F1",
      "name": "Signup",
      "steps": ["SCR1", "SCR2"],
      "missingStates": [],
      "confidence": "medium"
    }
  ],
  "interactions": [],
  "responsiveRules": [],
  "assets": [],
  "assumptions": [],
  "unresolvedQuestions": [],
  "confidence": "medium"
}
```

## Conventions

- Use stable IDs (`S1`, `SCR1`, `C1`, `F1`) so docs can cross-reference the model.
- Use `unknown` instead of inventing data.
- Use `confidence` values: `high`, `medium`, `low`.
- Keep `unresolvedQuestions` aligned with `docs/figma-harness/ambiguity-log.md`.
- Mark `canonical: true` only after evidence or user confirmation.
