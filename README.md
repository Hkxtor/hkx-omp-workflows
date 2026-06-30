# HKX OMP Workflows

Core Everything Claude Code workflows adapted for Oh My Pi.

This package is intentionally small: it ports the workflow surfaces that map cleanly onto OMP's native extension package model. It does not modify OMP or HKX source trees.

## Load

Run once with an explicit extension package path:

```bash
omp -e ./hkx-omp-workflows
```

Or add the package to an OMP project config, using the path where this package is checked out:

```json
{
  "extensions": ["./hkx-omp-workflows"]
}
```

Place that JSON in `.omp/settings.json` for project-scoped loading.

To install globally into `~/.omp/agent/` (symlink where possible, copy fallback on Windows):

```bash
npm run install-global
```

## Commands

All commands use an `hkx-` prefix to avoid collisions with OMP built-ins.

| Command | Purpose |
|---|---|
| `/hkx-build-fix` | Detect build failures and fix them incrementally |
| `/hkx-checkpoint` | Create, compare, or list lightweight `.omp/checkpoints.log` workflow checkpoints |
| `/hkx-code-review` | Review local changes or a PR without posting externally by default |
| `/hkx-cost-report` | Generate a local cost report from OMP cost-tracking data |
| `/hkx-plan` | Produce an implementation plan and wait for confirmation |
| `/hkx-plan-prd` | Draft a lean PRD under `.omp/prds/` |
| `/hkx-project-init` | Propose an OMP project setup plan |
| `/hkx-quality-gate` | Run the repo's validation gates and report status |
| `/hkx-refactor-clean` | Refactor with scoped tests and behavior preservation |
| `/hkx-review-pr` | Orchestrate read-only PR or local diff review across available reviewer agents |
| `/hkx-security-scan` | Scan agent, config, secret, and dependency surfaces |
| `/hkx-skill-create` | Analyze git history to extract patterns and generate SKILL.md files |
| `/hkx-skill-health` | Audit health of all installed skills in the skill portfolio |
| `/hkx-test-coverage` | Identify and close meaningful coverage gaps |
| `/hkx-update-codemaps` | Generate token-lean architecture codemaps from local repo evidence |
| `/hkx-update-docs` | Refresh docs from source-of-truth files while preserving hand-written intent |
| `/hkx-workflow` | Research, plan, implement, verify, and review with OMP-native agents |
## Skills

| Skill | Purpose |
|---|---|
| `hkx-tdd-workflow` | Test-first implementation guidance adapted for OMP |
| `hkx-verification-loop` | Build, lint, test, security, and diff verification |
| `hkx-coding-standards` | Cross-language coding standards |
| `hkx-config-gc` | Garbage collection for OMP config — scan, review, and clean stale or orphaned items |
| `hkx-security-review` | Security review checklist |
| `hkx-frontend-patterns` | React and frontend implementation patterns |
| `hkx-backend-patterns` | API, persistence, and service-layer patterns |
| `hkx-typescript-workflow` | TypeScript and JavaScript development workflow |
| `hkx-python-workflow` | Python implementation, testing, and security workflow |
| `hkx-rust-workflow` | Rust implementation and cargo validation workflow |
| `hkx-go-workflow` | Go implementation and validation workflow |
| `hkx-agent-architecture-audit` | Agent harness architecture audit across prompts, tools, memory, MCP, retries, and rendering |
| `hkx-agent-harness-construction` | Action-space, tool, prompt, observation, and recovery design for OMP agents |
| `hkx-agent-introspection-debugging` | Debugging loops, retry storms, compaction drift, and repeated agent failures |
| `hkx-ai-regression-testing` | Regression testing for agent/provider/tool-call/streaming/sandbox behavior |
| `hkx-bun-runtime` | Bun-first TypeScript runtime, process, file IO, worker, and test guidance |
| `hkx-error-handling` | Robust error contracts across TypeScript, Rust, Python, providers, tools, and TUI rendering |
| `hkx-rust-patterns` | Rust patterns for native crates, FFI, async cancellation, and hot paths |
| `hkx-rust-testing` | Rust and native-binding test patterns for OMP crates |
| `hkx-engineering-pack` | Router for the Engineering Pack skills |
| `hkx-search-first` | Research-before-coding workflow for dependencies, integrations, tools, and abstractions |
| `hkx-iterative-retrieval` | Progressive context retrieval before agent handoff or unfamiliar changes |
| `hkx-intent-driven-development` | Acceptance criteria and risk framing for ambiguous or high-impact requests |
| `hkx-parallel-execution-optimizer` | Dependency-lane planning for safe OMP parallel tool and agent work |
| `hkx-gateguard` | Fact-forcing pre-action gate before risky edits, new files, or commands |
| `hkx-strategic-compact` | Context hygiene guidance for compacting at safe phase boundaries |
| `hkx-api-design` | REST, HTTP, JSON-RPC, webhook, tool-schema, and public API contract design |
| `hkx-api-connector-builder` | Add integrations by matching existing repo connector/provider patterns |
| `hkx-hexagonal-architecture` | Ports-and-adapters boundaries for durable service design and refactors |
| `hkx-database-migrations` | Safe schema, index, backfill, rollback, and zero-downtime migration workflow |
| `hkx-production-audit` | Local-evidence release, deploy, install, and production-readiness audit |
| `hkx-repo-scan` | Local repository inventory, ownership, vendored-code, and refactor-readiness audit |
| `hkx-codebase-onboarding` | Structured repo reconnaissance, architecture map, and onboarding guide workflow |
| `hkx-code-tour` | Reusable CodeTour-style walkthrough artifacts with verified anchors |
| `hkx-architecture-decision-records` | Capture durable architecture decisions as ADRs with context and tradeoffs |
| `hkx-documentation-lookup` | Current library/framework/API documentation lookup through configured MCP docs tools |
| `hkx-e2e-testing` | Browser, CLI, install, smoke, and critical-user-journey E2E testing workflow |
| `hkx-accessibility` | WCAG-oriented UI semantics, keyboard, focus, form, and screen-reader checks |
| `hkx-ops-pack` | Router for operational workflows |
| `hkx-terminal-ops` | Evidence-first local command execution and CI/build debugging |
| `hkx-github-ops` | GitHub issues, PRs, CI checks, releases, and repository automation |
| `hkx-project-flow-ops` | Issue/PR queue triage and execution-flow coordination |
| `hkx-deployment-patterns` | Release, deployment, health check, rollback, and artifact workflows |
| `hkx-docker-patterns` | Dockerfile, Compose, image, network, volume, and health-check patterns |
| `hkx-automation-audit-ops` | Read-only inventory of hooks, CI, scripts, MCP servers, wrappers, and jobs |
| `hkx-workspace-surface-audit` | Workspace repo, plugin, MCP, extension, env, rule, and command surface audit |
| `hkx-canary-watch` | Post-deploy URL, endpoint, asset, console, network, and performance checks |
| `hkx-mcp-server-patterns` | MCP tool/resource/prompt schema, transport, error, security, and ops guidance |
| `hkx-git-workflow` | Branch, commit, PR, conflict, history, and release workflow guidance |
| `hkx-safety-guard` | Guardrails for destructive commands, scoped writes, external mutation, and production work |
| `hkx-security-scan` | OMP config, extension, MCP, command, skill, rule, secret, and permission scan workflow |
| `hkx-benchmark` | Performance measurement, baseline comparison, and regression detection |
| `hkx-deep-research` | Multi-source web research with parallel subagents and cited reports |
| `hkx-exa-search` | Neural search via Exa MCP for web, code, and company research |
| `hkx-market-research` | Competitive analysis, market intelligence, and industry research |
| `hkx-plan-orchestrate` | Multi-step plan decomposition and agent chain design |
| `hkx-research-ops` | Evidence-first current-state research workflow |

This package ports 15 portable reviewer, documentation, build resolver, and architecture agents.


| `build-error-resolver` | Build and TypeScript error resolution specialist for minimal code changes and quick recovery |
| `code-architect` | Designs feature architectures by analyzing codebase patterns and providing implementation blueprints |
| `code-explorer` | Deeply analyzes codebase features by tracing execution paths, mapping architecture layers, and documenting dependencies |
| `code-reviewer` | General evidence-gated code reviewer for correctness, maintainability, security, performance, and tests |
| `code-simplifier` | Simplifies and refines code for clarity, consistency, and maintainability while preserving behavior |
| `doc-updater` | Documentation and codemap specialist for evidence-backed README, guide, and codemap updates |
| `go-build-resolver` | Go build, vet, linter, and module dependency resolution specialist |
| `go-reviewer` | Expert Go code reviewer specializing in idiomatic patterns, concurrency, error handling, and performance |
| `pr-test-analyzer` | PR test-quality reviewer focused on behavior coverage and regression risk |
| `python-reviewer` | Expert Python code reviewer specializing in PEP 8 compliance, idioms, type hints, security, and performance |
| `rust-build-resolver` | Rust build, compilation, borrow checker, and dependency error resolution specialist |
| `rust-reviewer` | Expert Rust code reviewer specializing in ownership, lifetimes, safety, error handling, and performance |
| `security-reviewer` | Security reviewer for auth, input, data, secrets, dependencies, and trust-boundary changes |
| `silent-failure-hunter` | Reviewer for swallowed errors, dangerous fallbacks, and missing failure propagation |
| `typescript-reviewer` | Expert TypeScript/JavaScript code reviewer specializing in safety, correctness, and patterns |

### Manual Activation Requirement

> **IMPORTANT**: OMP core currently does not automatically discover `agents/` directories inside extension packages.
> To use these agents, you must manually copy or symlink them into your local OMP project's agent folder:
>
> ```bash
> # Copy to project-level OMP agents folder
> cp hkx-omp-workflows/agents/*.md .omp/agents/
>
> # Or copy to user-level OMP agents folder
> cp hkx-omp-workflows/agents/*.md ~/.omp/agents/
> ```
>
> Once copied/linked, they will be discoverable by OMP's agent runner (e.g. `/agent <agent-name>`).

## Engineering Pack

The Engineering Pack groups general product-engineering workflows that are useful
across stacks:

`hkx-search-first`, `hkx-iterative-retrieval`,
`hkx-intent-driven-development`, `hkx-parallel-execution-optimizer`,
`hkx-gateguard`, `hkx-strategic-compact`, `hkx-error-handling`,
`hkx-api-design`, `hkx-api-connector-builder`,
`hkx-hexagonal-architecture`, `hkx-database-migrations`,
`hkx-production-audit`, `hkx-repo-scan`, `hkx-codebase-onboarding`,
`hkx-code-tour`, `hkx-architecture-decision-records`,
`hkx-documentation-lookup`, `hkx-e2e-testing`, and `hkx-accessibility`.

Use `hkx-engineering-pack` as a router when the task spans multiple engineering
surfaces.

## Ops Pack

The Ops Pack groups operational workflows:

`hkx-terminal-ops`, `hkx-github-ops`, `hkx-git-workflow`,
`hkx-project-flow-ops`, `hkx-deployment-patterns`, `hkx-docker-patterns`,
`hkx-automation-audit-ops`, `hkx-workspace-surface-audit`,
`hkx-canary-watch`, `hkx-mcp-server-patterns`, `hkx-safety-guard`, and
`hkx-security-scan`.

Use `hkx-ops-pack` for command execution, GitHub/PR/git flow, deployment,
automation, workspace-surface, MCP-server, safety, and security-scan operations.

## Language Rules And Extensions

This package includes common workflow rules, a small language rule pack for TypeScript, Python, Rust, and Go, plus two OMP extensions.

| Surface | Files |
|---|---|
| Common rules | `rules/hkx-common-security.md`, `rules/hkx-common-testing.md`, `rules/hkx-common-coding-style.md`, `rules/hkx-common-code-review.md`, `rules/hkx-common-development-workflow.md`, `rules/hkx-common-git-workflow.md`, `rules/hkx-common-patterns.md`, `rules/hkx-common-performance.md` |
| Language rules | `rules/hkx-typescript.md`, `rules/hkx-python.md`, `rules/hkx-rust.md`, `rules/hkx-go.md` |
| TTSR-style reminders | `rules/hkx-ts-no-console-log.md`, `rules/hkx-rust-no-unwrap.md`, `rules/hkx-python-no-bare-except.md` |
| Web rules | `rules/hkx-web-design-quality.md`, `rules/hkx-web-performance.md` |
| Notify-only extension | `extensions/hkx-language-quality.ts` |
| Pre-action gate extension | `extensions/hkx-gateguard.ts` |

The language-quality extension only notifies. It does not format files, edit files, or run build commands automatically. The gateguard extension blocks first access per file and destructive commands; disable with `HKX_GATEGUARD=off`.

## MCP

OMP loads `.mcp.json` from extension package roots automatically to configure default Model Context Protocol (MCP) servers.

- **Bundled Defaults**: `hkx-omp-workflows` includes `.mcp.json` at its root which exposes four default MCP servers (`github`, `context7`, `exa`, and `playwright`). Additional servers like `memory` and `sequential-thinking` are available in the reference catalog below.
- **Reference Catalog**: A sanitized reference catalog is located at `mcp-configs/mcp-servers.json` with various common servers and instructions on how to add them.
- **Disabling MCPs**: To disable or override these default servers, use the `disabledMcpServers` or `mcpServers` settings in the OMP project config (`.omp/settings.json`), rather than the environment variables or filters used in HKX.

## Validate

```bash
npm run validate
```

The validator checks required files, frontmatter, command naming, and common non-OMP leftovers.

## Conversion Scope

This is a core workflow package, not a full HKX mirror. Deferred surfaces include shell hook packs, session-history utilities, external wrapper commands, and large language-specific skill catalogs. See `docs/conversion-map.md`.

## Analytics

![Alt](https://repobeats.axiom.co/api/embed/30913d54fbca61c5d7b226b31440fad178e2606a.svg "Repobeats analytics image")
