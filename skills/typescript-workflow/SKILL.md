---
name: hkx-typescript-workflow
description: TypeScript and JavaScript development workflow for OMP projects.
---

# HKX TypeScript Workflow

Use when implementing or reviewing TypeScript, JavaScript, React, or Node changes.

## Read First

- Read nearby files for import style, test framework, logging, and runtime APIs.
- In Oh My Pi itself, follow `AGENTS.md`: prefer Bun APIs, static imports, and `bun check`.
- Check package scripts before choosing validation commands.

## Implementation

- Prefer precise types and narrowing over `any`.
- Keep imports top-level and static unless runtime loading is required.
- Validate untrusted data with existing schema or parser patterns.
- Use project logging instead of `console.log`.
- Keep UI code accessible and dimensionally stable.

## Testing

- Cover observable behavior, parsing boundaries, state transitions, and error mapping.
- Avoid global mutation in tests. Restore spies, timers, env, and filesystem state.
- Do not use placeholder assertions.

## Validation

Prefer local project commands. Common targets:

```bash
bun check
bun test path/to/test.ts
npm run lint
npm run build
```

Use the package manager already configured by the repo.
