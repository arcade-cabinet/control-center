# arcade-cabinet Control Center

Organization-level control center for **arcade-cabinet**.

## Purpose

- Manages CI/CD workflows for all repos in this org
- Syncs shared configuration files
- Connects to enterprise orchestration at `jbcom/control-center`

## Structure

```
control-center/
├── .github/workflows/     # Org sync workflows
│   └── sync.yml           # The sync engine
├── repository-files/      # Files synced to org repos
│   ├── always-sync/       # Files that are always overwritten in target repos
│   │   ├── .github/
│   │   │   └── workflows/
│   │   │       ├── ci.yml                    # Multi-stack CI (Node, Rust, Python)
│   │   │       └── ecosystem-connector.yml    # AI Automation connector
│   │   ├── CONTRIBUTING.md
│   │   └── LICENSE
│   └── initial-only/      # Files synced only if they don't exist
│       ├── .gitignore
│       └── README.md      # Template README
└── scripts/               # Sync scripts
```

## Supported Stacks

The `ci.yml` workflow automatically detects and supports:
- **Node.js**: Detects `package.json`, supports `pnpm` (via `pnpm-lock.yaml`) and `npm`.
- **Rust**: Detects `Cargo.toml`.
- **Python**: Detects `pyproject.toml`, `setup.py`, `requirements.txt`, or `main.py`.
- **Godot**: Detects `project.godot`.

## Sync Mechanism

The `Sync Files` workflow (`.github/workflows/sync.yml`) runs on every push to `repository-files/**`.
- **always-sync/**: Overwrites files in all non-archived repos (except `control-center` and `.github`).
- **initial-only/**: Only creates files if they are missing.

## Enterprise Integration

This control-center connects back to `jbcom/control-center` for:
- AI-powered PR reviews
- Issue triage and delegation (/jules, /cursor, @claude)
- CI failure auto-resolution
