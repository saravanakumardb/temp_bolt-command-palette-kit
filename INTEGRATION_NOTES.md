# Integration Notes

This repo provides reusable primitives for:

- Command palette (`Cmd+K`)
- Keyboard shortcut registry
- Action search + grouping
- Recent actions

Integration pattern:

- Copy `src/components/**` + any `src/lib/**` helpers into target app.
- Map `--ux-*` tokens to target app tokens.
