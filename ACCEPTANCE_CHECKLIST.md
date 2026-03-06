# Acceptance Checklist

- Before push: `git status` is clean except for the intended app source changes.
- Before push: review `git diff` and confirm no unrelated formatting/refactors.
- No `console.log`.
- No hardcoded colors.
- No network calls.
- Forbidden files are NOT committed: `.env*`, `.next/`, `node_modules/`, `.vercel/`.
- Components in `src/components/**`; no imports from `src/app/**`.
- `pnpm run check` passes.
- `pnpm run build` passes (`next build --webpack`).
