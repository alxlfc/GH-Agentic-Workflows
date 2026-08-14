---
emoji: 📊
name: Weekly Report Status
description: Publish a concise weekly activity report as a new issue.
on:
  schedule:
    - cron: "0 9 * * 1"
  workflow_dispatch:
permissions:
  contents: read
  issues: read
  pull-requests: read
  copilot-requests: write
strict: true
tools:
  github:
    mode: gh-proxy
    toolsets: [default]
safe-outputs:
  create-issue:
    title-prefix: "[weekly-report] "
    max: 1
    close-older-issues: true
---

# Weekly Report Status

Generate a concise activity report for the previous seven full days ending at workflow start (UTC).

Use GitHub data to summarize:
- commits
- issues
- pull requests

Publish the report in a new issue using the configured safe output.

If there was no activity in one or more categories, say so clearly in the report.
If there was no activity at all in the window, state that explicitly.

Keep the report concise and factual.
