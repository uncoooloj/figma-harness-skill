# Forward-Test Checklist

Use this checklist to evaluate whether another agent followed the harness on a realistic task. Do not inspect hidden reasoning; inspect artifacts, questions, diffs, and validation output.

## Intake

- Did the agent inventory every provided source before coding?
- Did it classify source purpose and platform?
- Did it identify duplicates, stale sources, or canonicality conflicts?
- Did it avoid pretending to inspect inaccessible Figma content?

## Ambiguity

- Did it classify ambiguity by severity?
- Did it ask structured questions for blocking/high decisions?
- Did it avoid asking low-value questions that did not affect implementation?
- Did it document assumptions it made?

## Design Model

- Did it create or update `.tmp/figma-harness/design-model.json` for complex inputs?
- Did components, tokens, flows, and screens trace back to sources?
- Did confidence levels reflect evidence?

## Implementation

- Did it build tokens/components/layouts before screens?
- Did it preserve supplied design rather than redesigning it?
- Did it follow the repo's existing framework and styling patterns?
- Did production code writes come after source/ambiguity gates?

## Review

- Did it run available build/lint/test checks?
- Did it compare rendered UI against canonical design evidence?
- Did it record a mismatch ledger?
- Did it fix blocking/high mismatches before handoff?

## Result

Mark the run:

- `pass`: all critical gates observed
- `partial`: minor gaps, no high-risk violation
- `fail`: coded before source truth, guessed high-impact decisions, or skipped visual review
