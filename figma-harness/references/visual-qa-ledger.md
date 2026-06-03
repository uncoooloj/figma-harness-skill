# Visual QA Mismatch Ledger

Use this ledger during the Review Gate. Functional checks do not replace visual fidelity checks.

## Ledger

| ID | Severity | Area | Design evidence | Render evidence | Expected | Actual | Fix | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| M1 | high | Header nav | Figma S1/Header | Browser 1440px | 16px gap | 24px gap | Update nav gap token | fixed |

## Severity

- `blocking`: Wrong screen, wrong canonical source, unusable layout, missing primary flow, or severe mobile overflow.
- `high`: Noticeable mismatch in layout, hierarchy, tokens, assets, component variants, or interaction state.
- `medium`: Polish mismatch that affects quality but not core comprehension.
- `low`: Minor, reversible difference that can be documented.

## Required Evidence

Capture or record:

- canonical Figma frame, screenshot, or export
- rendered implementation viewport and state
- viewport size
- interaction state
- validation command or browser/simulator method

## Pass Criteria

The implementation can pass only when:

- blocking/high mismatches are fixed or explicitly out of scope
- responsive behavior has been checked where relevant
- intentional deviations are documented
- the final rendered UI still matches the source after fixes
