# Design System Brief (Must Follow)

This repo is a **command palette + keyboard shortcuts kit** intended for production reuse.

## Non-negotiable rules

- No `console.log`.
- No network calls.
- No hardcoded colors (no hex/rgb/hsl). Use CSS variables only.

## Token usage

- Use `UX_TOKEN_CONTRACT.md`.
- Style via CSS variables (`--ux-*`) and Tailwind utilities.

## Component architecture

- Reusable components in `src/components/**`.
- Pages in `src/app/**` compose components.
- Components must NOT import from `src/app/**`.

## Accessibility

- Focus trap for dialogs/palette.
- `Esc` closes.
- Keyboard-first UX.
