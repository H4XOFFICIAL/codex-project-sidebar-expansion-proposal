# Proposed GitHub Issue

**Title:** Codex Desktop: restore inline project expansion in the sidebar

## Summary

Restore an optional inline project list beneath the **Projects** row in Codex Desktop. Keep the current full Projects directory, but add a disclosure chevron so users can switch projects without leaving the task they are viewing.

## Problem

The Windows sidebar currently presents Projects as a destination row with a create button. Opening it replaces the active task with the full-page directory. That directory is useful for search and management, but it adds a detour to frequent project switching and removes at-a-glance project access from the sidebar.

## Proposed UX

- Add a dedicated disclosure chevron before the Projects folder icon.
- Chevron toggles a compact inline list of pinned or recently updated projects.
- Projects label continues to open the full directory.
- Plus continues to create a project.
- Remember the expanded or collapsed state on the device.
- Cap the shortcut list and finish it with **View all projects**.
- Keep the three actions separate for clear pointer and keyboard behavior.

## Acceptance Criteria

- Project shortcuts can be revealed without navigating away from the active task.
- Disclosure, Projects navigation, and project creation remain separate controls.
- The disclosure exposes an accurate `aria-expanded` state and works by keyboard.
- Expansion preference persists across app restarts on the same device.
- Long names truncate without shifting or overlapping controls.
- Empty, loading, and error states preserve access to the full Projects directory.
- Existing project sorting behavior is reused rather than duplicated.

## Relationship to Existing Issues

- [#23825](https://github.com/openai/codex/issues/23825) documents earlier project expansion behavior and a loading problem inside expanded project groups.
- [#33077](https://github.com/openai/codex/issues/33077) covers ordering for projects already visible in the sidebar.

This request is complementary: it focuses on restoring optional inline project access alongside the newer full-page directory.

## Prototype

- [Interactive prototype](https://h4xofficial.github.io/codex-project-sidebar-expansion-proposal/)
- [One-page UX specification](https://github.com/H4XOFFICIAL/codex-project-sidebar-expansion-proposal/blob/main/project-sidebar-expansion-spec.md)

Current full-page navigation:

![Current full-page navigation](https://raw.githubusercontent.com/H4XOFFICIAL/codex-project-sidebar-expansion-proposal/main/project-sidebar-current.png)

Proposed inline expansion:

![Proposed inline expansion](https://raw.githubusercontent.com/H4XOFFICIAL/codex-project-sidebar-expansion-proposal/main/project-sidebar-proposed.png)

All prototype project names and task content are invented. The reporter's private project names and screenshots are not included.
