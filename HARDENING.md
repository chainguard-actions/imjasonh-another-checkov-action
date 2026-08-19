<!-- markdownlint-disable -->

# Hardening Report: imjasonh--another-checkov-action/v0.1.0

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `2`

Action **imjasonh--another-checkov-action/v0.1.0** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The workflow uses `actions/checkout@v5`, which is a mutable tag reference rather than a pinned 40-character commit SHA. This means the action could be silently updated to a different (potentially malicious) version without any change to the workflow file, creating a supply-chain risk. It should be pinned to a full SHA, e.g. `actions/checkout@11bd71901bbe5b1630ceea73d27597364c9af683 # v4`.

Locations:

- `.github/workflows/use-action.yml:22`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned `actions/checkout@v5` to its full commit SHA `fbc6f3992d24b796d5a048ff273f7fcc4a7b6c09` in `.github/workflows/use-action.yml` (line 22). The tag is preserved as a comment (`# v5`) for readability. No other findings were present — the workflow already had appropriate permissions blocks at both the workflow and job levels.

