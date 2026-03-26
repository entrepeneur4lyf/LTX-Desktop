---
name: add-or-update-linux-support
description: Workflow command scaffold for add-or-update-linux-support in LTX-Desktop.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-linux-support

Use this workflow when working on **add-or-update-linux-support** in `LTX-Desktop`.

## Goal

Add or improve Linux support, including icons, installer scripts, and documentation.

## Common Files

- `electron-builder.yml`
- `resources/icons/1024x1024.png`
- `resources/icons/128x128.png`
- `resources/icons/16x16.png`
- `resources/icons/24x24.png`
- `resources/icons/256x256.png`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit electron-builder.yml to add targets or update configuration.
- Add or update resources/icons/*.png for Linux icons.
- Update scripts/create-installer.sh and scripts/Dockerfile.linux-build for build process.
- Update documentation (README.md, docs/INSTALLER.md) to reflect Linux support.
- Modify electron/python-setup.ts if Python setup changes are needed.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.