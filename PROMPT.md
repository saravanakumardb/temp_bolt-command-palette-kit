# Bolt — Command Palette + Keyboard Shortcuts Kit (Micro-App)

Before you start: read and follow `DESIGN_SYSTEM_BRIEF.md`, `UX_TOKEN_CONTRACT.md`, `REPO_SCOPING_RULES.md`, and `ACCEPTANCE_CHECKLIST.md`.

## Mission

Build a production-grade **command palette + keyboard shortcuts kit** micro-app (Next.js App Router) that we can copy into:

- `dashboards/admin-web`
- `dashboards/tracker-web`
- product web apps

This is implementation-heavy: correctness, a11y, and clean component boundaries matter.

## Constraints

- Only modify files in this repository.
- pnpm only.
- Next.js 16 App Router, React 19, TypeScript strict.
- TailwindCSS v4.
- No network calls.
- No `console.log`.
- No hardcoded colors — use `--ux-*` CSS variables from `UX_TOKEN_CONTRACT.md`.
- Avoid unnecessary dependencies. If you add a dependency, justify why it is required.

## Must-have routes

- `/` overview landing
- `/palette` command palette demo
- `/shortcuts` shortcuts reference + editor demo
- `/integration` copy/paste integration guide page (UI-only)

## Core deliverable: Command palette

Build `CommandPalette` with:

- Open via `Cmd+K` (and `Ctrl+K` fallback)
- Search box
- Grouped actions (e.g., Navigation, Actions, Settings)
- Optional action keywords (alias terms)
- Recent actions (persist to localStorage)
- Favorites/pinned actions (localStorage)
- Keyboard navigation:
  - Up/Down
  - Enter to execute
  - Esc to close
- Mouse support

Accessibility requirements:

- Proper dialog semantics
- Focus trap while open
- Focus returns to opener on close
- ARIA labels for listbox/options

## Shortcuts registry

Create a small shortcuts registry system:

- `registerShortcut({ id, keys, description, scope })`
- Scopes: global vs page-specific (simple; no complex routing coupling)
- A `/shortcuts` page that lists all registered shortcuts
- A UI to remap a shortcut (client-side only) and persist to localStorage
- Collision detection (warn if two actions use the same key combo)

## Demo content

Include 20–30 demo actions:

- Navigation actions to pages
- Theme toggle
- “Copy JSON” demo action
- “Clear local data” demo action with confirm dialog

## Deliverables

- Full Next.js app with scripts:
  - `dev`
  - `check` (must run `tsc --noEmit` + `eslint`)
  - `build` (must run `next build --webpack`)

## Verification

From repo root:

- `pnpm install`
- `pnpm run check`
- `pnpm run build`

## Output expectation

Open a PR that only changes files in this repo.
