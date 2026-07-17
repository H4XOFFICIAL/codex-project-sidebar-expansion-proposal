# Codex Project Sidebar Expansion Proposal

Codex Desktop should let users switch projects without replacing the task they are currently viewing. This proposal restores an optional inline project list beneath the existing **Projects** row while preserving the full Projects directory for search and management.

## The Proposal

- Add a dedicated disclosure chevron before the Projects folder icon.
- Let the chevron expand or collapse project shortcuts in place.
- Keep the Projects label as the route to the full directory.
- Keep the plus button as the create-project action.
- Remember the expanded state on the device.
- Show a compact set of pinned or recently updated projects followed by **View all projects**.
- Preserve keyboard navigation, visible focus, truncation, and tooltips for long names.

## Review Package

- [Live interactive prototype](https://h4xofficial.github.io/codex-project-sidebar-expansion-proposal/)
- [One-page UX specification](project-sidebar-expansion-spec.md)
- [Proposed `openai/codex` issue](github-issue-draft.md)
- `project-sidebar-current.png`: current full-page navigation state
- `project-sidebar-proposed.png`: proposed inline expansion state

Repeatable prototype states:

- Proposed expanded view: `index.html?mode=proposed&expanded=1&capture=1`
- Proposed collapsed view: `index.html?mode=proposed&expanded=0&capture=1`
- Current behavior: `index.html?mode=current&capture=1`

## Related Requests

- [openai/codex#23825](https://github.com/openai/codex/issues/23825) documents prior project expansion behavior and a loading problem within expanded groups.
- [openai/codex#33077](https://github.com/openai/codex/issues/33077) covers ordering of projects already shown in the sidebar.

This proposal does not duplicate either request. It focuses on retaining inline project switching alongside the newer full Projects directory.

## Privacy

The supplied reference screenshots were used only to understand the interaction. All names and content in the prototype are invented, and the original screenshots are not included in this repository.

## Status

Interaction, accessibility, and responsive-layout review passed. The proposal repository and prototype are approved for public submission to `openai/codex`.
