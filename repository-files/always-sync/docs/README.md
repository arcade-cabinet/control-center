# Documentation Repository

This directory contains the synthesized documentation for the arcade-cabinet organization.

## Structure
- `api/`: API documentation generated from code repositories.
- `guides/`: Human-written guides and tutorials.
- `specs/`: Technical specifications and RFCs.
- `branding/`: Organization-wide design system and branding assets.

## Sync Flow
1. Code repositories build their documentation (e.g., Sphinx, TypeDoc, rustdoc).
2. The `doc-sync` workflow in each repository pushes the built artifacts to this repository.
3. This repository hosts the unified documentation site.

