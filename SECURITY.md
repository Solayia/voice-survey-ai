# Security Policy

VoiceSurvey AI handles sensitive data — contact lists, recorded/transcribed
phone conversations, and survey responses. Security is a first-class concern.

## Reporting a vulnerability

If you discover a security vulnerability:

1. **Do not** open a public issue.
2. Report it **privately** to the project owner / security lead.
3. Include: a description, steps to reproduce, affected components, and impact.
4. Allow reasonable time for remediation before any wider disclosure.

Reports are acknowledged and triaged as a priority.

## Scope

This policy covers the application code, infrastructure configuration, and
data-handling pipelines in this repository.

## Data protection principles

- **Least privilege** for all credentials and service accounts.
- **Secrets never committed** — use environment variables and a secrets manager.
- **Encryption** in transit (TLS) and at rest for sensitive data.
- **PII handling** for contacts and call data must follow applicable
  regulations and the company's data-protection policy.
- **Auditability** — security-relevant actions should be logged.

Detailed controls are documented in
[`docs/17_SECURITY.md`](docs/17_SECURITY.md) and
[`docs/16_AUTHENTICATION.md`](docs/16_AUTHENTICATION.md).

## Supported versions

As an internal application under active development, only the current
`main` line is supported. Security fixes are applied to the latest version.
