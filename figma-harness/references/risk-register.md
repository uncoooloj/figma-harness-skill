# Product Risk Register

Use this when a design-to-code decision could affect product behavior, security, data, payments, permissions, or user trust.

```md
# Product Risk Register

| ID | Risk | Severity | Source | Decision needed | Owner | Mitigation | Status |
| --- | --- | --- | --- | --- | --- | --- | --- |
| R1 | Signup flow may use stale phone-first design | high | S1/S2 conflict | Choose canonical flow | user | Ask before coding | open |
```

## Severity

- `blocking`: could ship wrong product behavior, expose data, break payment/auth, or require major rewrite
- `high`: likely rework or user-facing behavior mismatch
- `medium`: quality or maintainability risk
- `low`: minor reversible risk

## Rules

- Do not hide product risk inside implementation notes.
- Link risks to source IDs and ambiguity IDs.
- Mark mitigations as confirmed, assumed, or blocked.
- Carry unresolved blocking/high risks into the final response.
