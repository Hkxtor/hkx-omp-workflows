---
description: Inspect a project and propose an OMP-native setup plan for commands, skills, rules, MCP, and validation.
argument-hint: "[project goal or stack]"
---

# HKX Project Init For OMP

Prepare an OMP setup plan for: `$ARGUMENTS`

Default to dry run. Do not modify project guidance, settings, rules, skills, or credentials until the user approves a concrete plan.

## Inspect

Read:

- `AGENTS.md`
- Existing `.omp/`, `.codex/`, `.gemini/`, `.opencode/`, `.cursor/`, and editor guidance
- Package manifests and CI config
- Test, lint, build, and format scripts
- Existing MCP configuration

## Recommend

Produce a plan for:

- `.omp/commands/` project commands
- `.omp/skills/` project skills
- `.omp/rules/` rulebook entries
- `.omp/settings.json` extension or MCP entries
- Validation commands
- Security boundaries for external actions

## Preserve

- Never overwrite existing guidance blindly.
- Prefer append or merge plans with explicit diffs.
- Keep credentials out of committed files.
- Keep user-level config separate from project-level config.

## Output

Return:

- Current state summary
- Proposed files and actions
- Risks
- Exact validation commands
- Confirmation prompt before writes
