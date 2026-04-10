# Transcendence Monorepo Skeleton

This repository now includes a feature/domain-oriented monorepo structure to support the Five Seas project.

## Top-level layout

- `apps/`: user-facing applications
- `packages/`: shared libraries and contracts
- `services/`: auxiliary runtime services
- `infra/`: container, database, and deployment assets
- `tests/`: automated test suites by scope
- `docs/`: architecture and decision records
- `Rules/`: game design and balancing documentation

## Why this structure

- Enables parallel work for the 5 team roles.
- Keeps game logic deterministic and reusable.
- Avoids tight coupling between UI, server, and persistence.
- Supports real-time multiplayer and simulation testing early.

## Existing folders

`include/` and `src/` were kept untouched to allow side-by-side comparison before migration.
