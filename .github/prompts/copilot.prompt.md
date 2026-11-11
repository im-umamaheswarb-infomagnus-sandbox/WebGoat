---
name: "WebGoat Security Review"
description: "Explicitly review or implement a WebGoat security change, including input validation, parameterized queries, and secret handling."
argument-hint: "Describe the code or security change to review"
agent: "agent"
---

Review or implement the requested security change in WebGoat. Follow the [WebGoat project instructions](../instructions/webgoat.instructions.md).

- First determine whether the affected code is an intentionally vulnerable lesson. Preserve its learning objective, expected vulnerability, and challenge behavior unless the request explicitly asks to change them.
- In application and support code outside intentionally vulnerable lessons, use parameterized queries and never build queries by concatenating untrusted input.
- Validate external input and encode output for its specific context.
- Never hard-code secrets. Use environment variables or an approved secret manager.
- Read the relevant implementation and tests before changing behavior. Add or update focused tests; changes to lessons require an integration test.
- Keep any implementation limited to the requested task and owning Maven module.
- Summarize security findings or changes, affected files, and tests run. If reviewing without changes, list findings by severity and state when no findings were identified.