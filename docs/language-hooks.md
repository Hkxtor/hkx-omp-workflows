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

## Extensions

### hkx-language-quality.ts

Post-execution notification extension.

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

### hkx-gateguard.ts

Pre-execution fact-forcing gate extension.

Current behavior:

- Intercepts `tool_call` events for `edit`, `write`, `ast_edit`, and `bash` before execution.
- Blocks first access to each file with investigation questions (which importers, schemas, user instruction).
- Blocks destructive Bash commands (`rm -rf`, `git push --force`, `DROP TABLE`, etc.).
- Tracks per-session state so a file passes the gate after the first denial.
- Condenses denial messages after the first three full denials to prevent context bloat.

Disable per-session:

```text
HKX_GATEGUARD=off
```

It does not:

- Auto-investigate files
- Run commands on the agent's behalf
- Persist state across sessions

Complementary surfaces:

- `skills/gateguard/SKILL.md` — prompt-level gate guidance and output format.
- `skills/safety-guard/SKILL.md` — runtime safety checks (non-overlapping).

## Future Additions

Good next migrations:

- Separate optional auto-fix extension with explicit settings.
- Per-language skill packs for Python, Rust, Go, Java, Kotlin, Swift, and frontend frameworks.
- Project-local rule overlays under `.omp/rules/` for repo-specific standards.
