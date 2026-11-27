# Architecture: `speckit-superpowers-bridge` in Dark Gravity

## Ecosystem Role & Tier

- **Tier**: `orchestration_bridge`
- **Role**: Governance contract separating specification/planning (`WHAT`, owned by `spec-kit`) from implementation execution (`HOW`, owned by `superpowers`) across all Dark Gravity autonomous factory missions and developer sessions.
- **Visibility**: `public`

## Internal Component Design

- `extension.yml`: Registers Spec-Kit lifecycle hooks (`before_clarify`, `before_plan`, `before_tasks`, `before_implement`, `after_tasks`) into target repositories.
- `scripts/` (`bash` & `powershell`): Implements `guard-command`, `update-handoff`, `bridge-state`, and `common-actor-resolution` reading/writing `.specify/superpowers-handoff.json`, `.specify/bridge-events.jsonl`, and `.specify/bridge-snapshots/` with SHA-256 artifact drift tracking.
- `tests/` & `docs/`: Contract and integration regression suites verifying mutually exclusive ownership boundaries across Claude Code and Codex harnesses.

## Upstream & Downstream Ecosystem Interfaces

```text
spec-kit (/speckit-specify, /speckit-plan, /speckit-tasks)
   │
   ▼  after_tasks hook (status: ready)
speckit-superpowers-bridge (.specify/superpowers-handoff.json + guard-command)
   │
   ├──► Enforces mutual exclusion (blocks speckit.implement & duplicate superpowers:writing-plans)
   ▼
superpowers / ZeroClawAgent execution (executing-plans, TDD, verification-before-completion)
   └──► status: complete (diff drift check) -> Vertex 4 HITL PR Review in rust_CACD_autonomous_factory
```

## Security Boundary & Governance

- **Anti-Drift Contract Enforcement**: Prevents autonomous agents from silently rewriting design contracts mid-implementation or skipping human Vertex 2 plan approval.
- **`DOC-011` Public Boundary**: Contains zero private repo names, cluster credentials, or internal IPs; upstream policy documented in `UPSTREAM_AND_FORK_POLICY.md`.

## Canonical Cross-Links

- [DARK_GRAVITY_MANIFEST.md](./DARK_GRAVITY_MANIFEST.md)
- [REPOSITORIES.md](./REPOSITORIES.md)
- [Global Architecture Portal](https://lgcorzo.github.io/architecture.html)
- [Unified Start-Here Portal](https://lgcorzo.github.io/start-here)
- [AI Auditor Pack](https://lgcorzo.github.io/docs/auditor/)
