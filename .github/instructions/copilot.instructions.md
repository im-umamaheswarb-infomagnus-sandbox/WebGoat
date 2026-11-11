
---
name: "Copilot Instructions"
description: "Project-wide guidance for OWASP WebGoat development, intentionally vulnerable lessons, Maven modules, testing, and security."
applyTo: "**/*"
---
# Copilot Instructions

## Project Context

- WebGoat is an OWASP application intentionally designed to be vulnerable for security education. Preserve lesson vulnerabilities and expected challenge behavior unless a task explicitly asks to change them.
- Keep changes focused on the requested task and the owning Maven module. Preserve existing APIs and lesson contracts unless a behavior change is explicitly requested.
- Use Copilot to assist with code generation, but always review and validate suggestions for security and correctness.

## Development and Testing

- Read the relevant implementation and tests before changing behavior.
- Add or update tests for changed code. Changes to lessons require an integration test.
- Follow the repository's configured Checkstyle and PMD rules.
- Use the Maven wrapper (`mvnw.cmd` on Windows or `./mvnw` on Linux/macOS) and run focused tests for the affected module.

## Security Rules

- Never hard-code secrets. Read them from environment variables or an approved secret manager.
- In application and support code outside intentionally vulnerable lessons, use parameterized queries and validate and context-appropriately encode external input.
- Use approved cryptographic algorithms; do not use MD5 or SHA-1.
- Pin dependency versions and prefer packages with no known vulnerabilities.
- Grant `GITHUB_TOKEN` the least privileges required in GitHub Actions workflows, and pin actions to full commit SHAs.
- Log errors without exposing secrets or other sensitive data.
