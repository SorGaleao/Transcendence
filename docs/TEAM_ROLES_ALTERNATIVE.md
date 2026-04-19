# 👥 Alternative Team Structure — Transcendence Project (Five Seas: Fisher Clash)

# 🧠 1. Core (Gab, Tania, Keillin)

## Ownership
- All integration-heavy, cross-feature, and architectural work
- Core game engine, networking/session, and at least one major feature (e.g., movement or economy)
- Contracts, integration, and code reviews

## Responsibilities
- Define and maintain all game data contracts
- Ensure consistency of game rules across all systems
- Review all rule-related pull requests
- Pair-program, review each other’s work, and handle the most complex, interdependent parts

## Deliverables
- Core game engine (pure logic layer)
- Networking and session system
- Integration and deployment pipeline
- Rule resolution system

---

# 🏝️ 2. Feature Leads (Ana Paula, Samir)

## Ownership
- Self-contained features with clear API boundaries
- Examples: bots/hazards, fishing/economy, spectator/statistics module

## Responsibilities
- Develop and test features in isolation
- Own backend logic, DB schema (as needed), and UI for their slice
- Ensure their work can be plugged in via well-defined interfaces
- Request integration support from the Core Trio as needed

## Deliverables
- Complete feature implementation (backend + frontend)
- Documentation of API boundaries
- Unit and integration tests for their feature

---

# 🔄 Integration & QA

- The Core Trio is responsible for all integration, code review, and system-wide QA.
- Feature Leads focus on delivering their features with minimal dependencies.
- Regular integration checkpoints ensure smooth merging of isolated features.

---

# 🔥 Global Architecture Rules

- Core owns all contracts, integration, and architectural decisions.
- Isolated Feature Leads own their feature end-to-end, but must adhere to defined interfaces.
- All code merges and integration go through the Core Trio.

---
