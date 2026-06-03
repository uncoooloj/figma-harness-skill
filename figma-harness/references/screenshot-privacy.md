# Screenshot Privacy

Screenshots can expose private product plans, customer data, credentials, internal names, unreleased UI, or paid assets. Minimize what you capture and where you publish it.

## Rules

- Capture only the region needed to answer the question.
- Redact customer names, emails, tokens, account IDs, balances, and private operational data.
- Do not upload private screenshots to public issues, PRs, or READMEs unless the user explicitly confirms they are safe to publish.
- Prefer local `docs/figma-harness/images/` paths for private work and mention that the files should not be committed if they contain sensitive material.
- Use textual descriptions instead of screenshots when redaction would destroy the evidence.

## Public Repo Safety

For public repositories:

- Do not commit screenshots from non-public Figma files by default.
- Do not include private screenshot links in PR bodies.
- Use screenshot manifests to describe evidence without embedding the image when needed.
- If evidence must be shared, ask whether to attach a redacted image.

## Redaction Notes

Record redaction in the manifest:

```md
| IMG2 | source-crop | S3 | Billing table | 1440x900 | local only | A4 | Customer names redacted |
```

## Clarification Message

When privacy prevents returning an image, say so directly:

```text
I can see the ambiguous billing-table region, but it includes customer data. I am describing the region instead of attaching the screenshot.
```
