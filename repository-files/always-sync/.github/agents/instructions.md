# Agentic Instructions (DRY)

This document contains the consolidated agentic instructions used by all AI agents in the arcade-cabinet organization.

## Core Directives
1. **Security First**: Never expose secrets. Use `GH_TOKEN` or `CI_GITHUB_TOKEN`.
2. **Standard Stack**: Focus on Python 3.12, Node.js 22, Rust Stable, and Go 1.22.
3. **CI/CD Integration**: Always ensure CI passes before suggesting a merge.
4. **Documentation**: Build and verify documentation updates as part of feature delivery.

## Tooling
- Use `vendor-connectors` for all vendor-specific operations.
- Use `gh` CLI for GitHub interactions.
- Use `actionlint` for workflow validation.

## Review Standards
- Follow conventional commits: `feat`, `fix`, `docs`, `chore`, `refactor`, `test`.
- Maintain the Memory Bank protocol in `memory-bank/*.md`.
- Adhere to the jbcom design system for all documentation.
