# Language Rules And Extensions

HKX language migration uses two OMP surfaces.

## Rules

Language guidance belongs in `rules/*.md` with OMP frontmatter:

```md
---
description: TypeScript and JavaScript coding guidance
globs:
  - "**/*.{ts,tsx,js,jsx}"
---
```

Use `globs`, not the HKX/Claude `paths` field.

Rules are best for:

- Coding style
- Testing policy
- Security reminders
- TTSR patterns such as `console.log`, bare `except`, or Rust `unwrap`

## Extension

Executable extension behavior belongs in `extensions/hkx-language-quality.ts`.

Current behavior:

- Observes successful `edit`, `write`, and `ast_edit` tool results.
- Extracts touched file paths from tool input and details.
- Shows a UI notification listing suggested validation checks.
- Logs a debug entry for diagnostics.

It does not:

- Auto-format files
- Run build commands
- Modify files
- Block tool calls

That default keeps the pack safe for projects that have not opted into automatic command execution.

## Future Additions

Good next migrations:

- Separate optional auto-fix extension with explicit settings.
- Per-language skill packs for Python, Rust, Go, Java, Kotlin, Swift, and frontend frameworks.
- Project-local rule overlays under `.omp/rules/` for repo-specific standards.
