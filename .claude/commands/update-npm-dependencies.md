---
name: update-npm-dependencies
description: Workflow command scaffold for update-npm-dependencies in LTX-Desktop.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /update-npm-dependencies

Use this workflow when working on **update-npm-dependencies** in `LTX-Desktop`.

## Goal

Upgrade or update JavaScript/TypeScript dependencies for the project.

## Common Files

- `package.json`
- `pnpm-lock.yaml`
- `pnpm-workspace.yaml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit package.json to update dependency versions.
- Regenerate pnpm-lock.yaml to reflect new versions.
- Update pnpm-workspace.yaml if workspace structure changes.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.