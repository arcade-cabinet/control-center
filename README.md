# arcade-cabinet Control Center

Organization-level control center for **arcade-cabinet**.

## Purpose

- Manages CI/CD workflows for all repos in this org
- Syncs shared configuration files (always-sync and initial-only)
- Syncs organization secrets across all repositories
- Configures repository settings (labels, branch protection, etc.)
- Connects to enterprise orchestration at `jbcom/control-center`

## Structure

```
control-center/
├── .github/workflows/     # Org sync workflows
├── repository-files/      # Files synced to org repos
│   ├── always-sync/       # Shared configs (Workflows, AI rules)
│   └── initial-only/      # Project templates (Python, Node, Rust)
├── scripts/               # Management scripts (Secrets, Config, Sync)
└── repo-config.json       # Central registry of repositories and settings
```

## Management Scripts

- `scripts/sync-files`: Syncs files from `repository-files/` based on ecosystem.
- `scripts/sync-secrets`: Syncs GHA secrets from control-center to all repos.
- `scripts/configure-repos`: Standardizes repository settings (labels, merge rules).
- `scripts/sync-projects`: (Optional) Syncs items to organization projects.

## Usage

Repos in this org automatically receive:
- **CI Workflows**: Multi-stack support (Python, Node, Rust, Go) with automated documentation building.
- **AI Automation**: Connection to enterprise AI review and delegation via `ecosystem-connector`.
- **Branding**: Unified documentation branding and Cursor rules.

## Enterprise Integration

This control-center connects back to `jbcom/control-center` for:
- AI-powered PR reviews (Tiered: Ollama → Claude → Jules)
- Issue triage and delegation (`/jules`, `/cursor`, `@claude`)
- CI failure auto-resolution
- Unified design system and brand standards

---
*Managed by arcade-cabinet/.github and arcade-cabinet/control-center*
