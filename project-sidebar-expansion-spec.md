# Restore Inline Project Expansion in Codex Desktop

**Surface:** ChatGPT Windows desktop app, Codex mode  
**Scope:** Sidebar project navigation only  
**Status:** Focused UX proposal

## Problem

The Projects item now opens a full-page directory. That page is useful for search and project management, but it turns a frequent context switch into a navigation detour: leave the active task, open Projects, choose a project, then select work. The supplied Windows reference shows no inline disclosure control.

Project expansion is an established desktop pattern in adjacent reports. [#23825](https://github.com/openai/codex/issues/23825) discusses loading threads when project groups expand, while [#33077](https://github.com/openai/codex/issues/33077) discusses ordering projects in the sidebar. Neither asks to preserve inline project access alongside the full directory.

## Goal

Restore fast, optional project switching without removing or weakening the full Projects directory.

## Proposed Interaction

1. Add a disclosure chevron before the Projects folder icon.
2. Chevron click toggles project shortcuts inline and updates `aria-expanded`.
3. Projects label click opens the full directory exactly as it does today.
4. Plus click continues to open project creation.
5. Expanded content shows pinned projects first, then recently updated projects, capped to a compact list with **View all projects**.
6. Selecting a shortcut switches project context while keeping the sidebar available.
7. Expansion state persists locally across app restarts. Project selection and directory navigation do not silently change that preference.

## States

- **Collapsed:** only the Projects row is visible; chevron points right.
- **Expanded:** shortcuts appear below the row; chevron points down.
- **Empty:** show **No projects yet** and keep the plus action available.
- **Loading:** reserve row height and show a subtle progress state without shifting navigation.
- **Unavailable:** keep the Projects directory reachable and offer retry inline.
- **Long names:** single-line truncation with the full name available on hover or focus.

## Accessibility and Keyboard

- Use separate native controls for disclosure, directory navigation, and creation.
- Give the disclosure control `aria-controls` and an accurate `aria-expanded` value.
- Preserve logical tab order and visible focus.
- Left/Right may collapse or expand when focus is on the disclosure; Enter/Space activate the focused control.
- Do not rely on icon orientation or color alone; accessible labels must say **Expand projects** or **Collapse projects**.

## Acceptance Criteria

- A user can reveal project shortcuts without leaving the current task.
- Projects label still opens the full directory, and plus still starts creation.
- Expanded or collapsed preference survives restart on the same device.
- A project shortcut is reachable and activatable by keyboard.
- The sidebar remains stable with long names, empty data, loading, and errors.
- The shortcut list has a clear cap and always exposes **View all projects**.
- Existing project sorting rules are respected; this proposal does not invent a second ordering model.

## Non-Goals

- Replacing the full Projects directory.
- Redesigning project creation, pinning, editing, or sorting.
- Changing project or task persistence APIs.
- Displaying private folder paths in the sidebar.

## Prototype Note

The prototype uses invented project names and local simulated state. It demonstrates interaction only and does not connect to an account or project backend.
