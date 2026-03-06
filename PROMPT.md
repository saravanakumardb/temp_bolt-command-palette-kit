# Bolt — Command Palette + Keyboard Shortcuts Kit

**GitHub repo:** `saravanakumardb/temp_bolt-command-palette-kit`

## Push Instructions

- Push directly to `main` — do NOT open a PR
- Only modify files in this repo

## Rules

- No `console.log`
- No network calls — mock data / localStorage only
- No hardcoded colors — no hex, no rgb/rgba/hsl, no `bg-[#123456]` Tailwind classes
- Do NOT commit `.env*`, `.next/`, `node_modules/`, `.vercel/`
- pnpm only
- `pnpm run check` must pass (`tsc --noEmit` + `eslint`)
- `pnpm run build` must pass (`next build --webpack`)

## CSS Token Contract

Define in `src/app/globals.css` under `:root` (add `.dark` override):

- `--ux-bg` — page background
- `--ux-surface` — card/panel surface
- `--ux-surface-2` — elevated surface
- `--ux-border` — borders
- `--ux-text` — primary text
- `--ux-text-muted` — secondary text
- `--ux-accent` — primary accent
- `--ux-accent-foreground` — text on accent
- `--ux-danger` — destructive/error
- `--ux-warning` — warning
- `--ux-success` — success
- `--ux-ring` — focus ring
- `--ux-shadow` — shadows

Use only via Tailwind: `bg-[var(--ux-surface)]`, `text-[var(--ux-text)]`, `border-[var(--ux-border)]`

## Component Architecture

- Reusable components → `src/components/`
- Pages in `src/app/**` compose components only
- Components must NOT import from `src/app/**`

## Stack

- Next.js 16 App Router, React 19, TypeScript strict
- TailwindCSS v4, pnpm

## Mission

Build a production-grade **command palette + keyboard shortcuts kit** micro-app reusable across `dashboards/admin-web`, `dashboards/tracker-web`, and product web apps.

## Pages

- `/` overview landing
- `/palette` command palette demo
- `/shortcuts` shortcuts reference + editor
- `/integration` copy/paste integration guide (UI-only)

## Command Palette

- Open via `Cmd+K` (and `Ctrl+K` fallback)
- Search box with grouped actions (Navigation, Actions, Settings)
- Optional action keywords (aliases)
- Recent actions + favorites/pinned (localStorage)
- Keyboard: Up/Down, Enter to execute, Esc to close
- Mouse support
- Dialog semantics, focus trap, focus returns on close, ARIA labels

## Shortcuts Registry

- `registerShortcut({ id, keys, description, scope })`
- Scopes: global vs page-specific
- `/shortcuts` page listing all registered shortcuts
- Remap shortcuts UI (localStorage), collision detection

## Demo Content

20–30 demo actions: navigation, theme toggle, "Copy JSON", "Clear local data" (confirm dialog)

## Verification

```
pnpm install && pnpm run check && pnpm run build
```
