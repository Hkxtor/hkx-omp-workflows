# Agent Guidelines

## Core Identity

You are working in `hkx-omp-workflows`, an OMP-native extension package that ports a small, useful core of Everything Claude Code workflows into Oh My Pi.


## Package Scope

This package is intentionally small. It is not a full HKX mirror.

Included surfaces:

- `commands/`: OMP slash commands, all using the `hkx-` prefix.
- `skills/`: OMP skills converted from HKX or synthesized for OMP workflows.
- `rules/`: common, language, web, and reminder rules for OMP sessions.
- `agents/`: portable agent definitions adapted to OMP canonical tools.
- `extensions/hkx-language-quality.ts`: notify-only language-quality extension.
- `extensions/hkx-gateguard.ts`: pre-action fact-forcing gate extension using OMP `tool_call` hook.
- `.mcp.json` and `mcp-configs/`: default and reference MCP configuration surfaces.
- `docs/conversion-map.md`: authoritative migration map from HKX to OMP.

Deferred surfaces stay out of this core package unless the user explicitly asks for a new optional pack:

- framework/domain-specific HKX agents and skills,
- shell hook packs and hookify flows,
- external wrapper commands,
- session-history utilities tied to a different store,
- continuous-learning scripts tied to another home-directory layout,
- large language-specific catalogs.

## Required Workflow

1. Search first. Before adding or replacing any command, skill, rule, agent, extension, helper, dependency, or MCP entry, check existing package surfaces and `docs/conversion-map.md`.
2. Reuse the OMP package pattern already present. Do not introduce a second convention beside an existing one.
3. Keep migrations OMP-native. Remove HKX-specific assumptions instead of carrying compatibility shims.
4. Prefer compact workflow guidance over long HKX source tutorials. This package should stay readable and maintainable.
5. Verify with `npm run validate` from `hkx-omp-workflows` after changing commands, skills, rules, agents, extensions, package metadata, or MCP config.

## Surface Conventions

### Commands

- File names must start with `hkx-`.
- Frontmatter must include `description`; include `argument-hint` when useful.
- Commands should describe OMP-native tool usage, not external wrapper runtimes.
- Use `.omp/plans/` and `.omp/prds/` for generated planning artifacts, `.omp/checkpoints.log` for checkpoint logs, and `docs/CODEMAPS/` for codemap output.

### Skills

- Each skill lives at `skills/<name>/SKILL.md`.
- Frontmatter `name` must be `hkx-<folder-name>`.
- Frontmatter must include `description`; keep `origin: HKX-converted-for-OMP` for converted skills.
- Adapt instructions to OMP tools, OMP extension packages, OMP MCP loading, and local repo evidence.
- Do not copy large HKX examples unless they are essential to the OMP workflow.
- CodeTour artifacts use `.tours/` unless a repository documents a different tour path.

### Rules

- Rule files live under `rules/` and use frontmatter with `description`.
- Common rules use `hkx-common-*` names.
- Language rules use `hkx-typescript.md`, `hkx-python.md`, `hkx-rust.md`, and `hkx-go.md`.
- Web rules use focused `hkx-web-*` names.
- Reminder rules should be narrow and prompt-time friendly; runtime enforcement belongs in the extension.

### Agents

- Agent frontmatter `name` must match the file basename.
- `tools` must use OMP canonical tool names accepted by `scripts/validate.mjs`.
- Agents in this extension package are portable definitions. OMP core may not auto-discover extension `agents/`; users may need to copy or symlink them into `.omp/agents/` or `~/.omp/agents/`.
- Keep agent responsibilities narrow: reviewers review, build resolvers fix build/type/test failures with minimal diffs.
- `agent-evaluator` is a meta-evaluator of agent output (5-axis scorecard: accuracy, completeness, clarity, actionability, conciseness). It is orthogonal to `code-reviewer` and the language reviewers, which review code — `agent-evaluator` reviews what an agent delivered against what was asked. Pair it with the `agent-self-evaluation` skill for an independent second-party assessment.

### Extensions

- `extensions/hkx-language-quality.ts` is notify-only. It must not format files, edit files, install packages, run builds, or mutate project state automatically.
- `extensions/hkx-gateguard.ts` blocks first edit/write per file and destructive commands via `tool_call`. Disable with `HKX_GATEGUARD=off`.
- Keep extension messages actionable and low-noise.

### MCP Config

- Root `.mcp.json` is the package default MCP surface loaded by OMP extension loading.
- `mcp-configs/mcp-servers.json` is a sanitized reference catalog.
- Do not reintroduce HKX-specific MCP filters or installer behavior.

## Quality Bar

- No secrets, tokens, credentials, private paths, or user-specific machine assumptions.
- No compatibility aliases or deprecated duplicate paths unless explicitly approved.
- No placeholder workflow text, no TODO-only surfaces, no fake validation claims.
- Keep language precise: OMP surfaces, OMP commands, OMP tools, OMP extension package model.
- If local evidence contradicts this file, update this file and the affected package surface together.

## Success Criteria

You are successful when:

- The requested OMP workflow surface is complete and internally consistent.
- `npm run validate` passes for package-surface changes.
- `README.md` and `docs/conversion-map.md` remain accurate when migration scope changes.
- The result is smaller, clearer, and more OMP-native than the HKX source it replaces.
