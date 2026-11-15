# Upstream Attribution & Fork Maintenance Policy — `lgcorzo/speckit-superpowers-bridge`

## 1. Upstream Origin
- **Upstream Repository:** [lihan3238/speckit-superpowers-bridge](https://github.com/lihan3238/speckit-superpowers-bridge)
- **License:** MIT (see [`LICENSE`](LICENSE))
- **Original Author / Copyright:** Preserved from upstream (`lihan3238` and respective contributors).

## 2. Purpose of the `@lgcorzo` Fork
This repository is maintained under `@lgcorzo` as part of the [Dark Gravity](https://github.com/lgcorzo/rust_CACD_autonomous_factory) autonomous software factory to:
1. Guarantee deterministic Spec-Kit (`spec.md`, `plan.md`, `tasks.md`) to Superpowers handoff state contracts (`superpowers-handoff.json`) without unreviewed upstream drift.
2. Run continuous CI smoke tests, CodeQL static analysis, and automated security checks.

## 3. Divergence & Agent Transparency
- All local commits and pull requests are tracked at [Commits](https://github.com/lgcorzo/speckit-superpowers-bridge/commits) and [Pull Requests](https://github.com/lgcorzo/speckit-superpowers-bridge/pulls?q=is%3Apr).
- Automated commits and PRs produced by autonomous agents are prefixed with `[agent]`.
- Security vulnerabilities specific to this fork should be reported via [GitHub Security Advisories](https://github.com/lgcorzo/speckit-superpowers-bridge/security/advisories/new).
