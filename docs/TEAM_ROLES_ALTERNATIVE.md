# 👥 Alternative Team Structure — Transcendence Project (Five Seas: Fisher Clash)


# 🧠 1. Core (Gab, Tania, Keillin)

## Ownership
- All integration-heavy, cross-feature, and architectural work
- Core game engine, networking/session, database, and at least one major feature (e.g., movement or economy)
- Contracts, integration, and code reviews
- Server-authoritative logic, event-driven architecture, and reconnection/state recovery

## Responsibilities
- Define and maintain all game data contracts (player state, seas, events, cards, cargo, coins, HP)
- Ensure consistency and enforcement of all official game rules (6-phase turn structure, movement, battle, fishing, hazards, cards, market, set collection, win/tiebreakers, etc.)
- Implement and maintain server-authoritative logic and event-driven architecture (WebSocket events)
- Implement and maintain reconnection and state recovery
- Review all rule-related pull requests
- Pair-program, review each other’s work, and handle the most complex, interdependent parts

## Deliverables
- Core game engine (pure logic layer)
- Networking and session system
- Database schema and persistence layer
- Integration and deployment pipeline
- Rule resolution system
- Event system (lobby, turn, move, combat, hazard, fishing, market, card, player state, game end)
- Reconnection and state recovery
- Match history and statistics tracking

---


# 🏝️ 2. Feature Leads (Ana Paula, Samir)

## Ownership
- Self-contained features with clear API boundaries
- Examples: bots/hazards, fishing/economy, cards, spectator/statistics module

## Responsibilities
- Develop and test features in isolation
- Implement all rules-driven requirements for their feature:
	- For fishing/economy: cargo limits, fish rarity, set bonuses, emergency sale, market, card effects
	- For bots/hazards: bot AI, hazard resolution, environmental damage, event triggers
	- For cards: card timing, effects, targeting, hand limits
- Own backend logic and UI for their slice (DB schema as needed, but must be reviewed by Core)
- Ensure their work can be plugged in via well-defined interfaces
- Request integration support from the Core Trio as needed

## Deliverables
- Complete feature implementation (backend + frontend)
- Documentation of API boundaries
- Unit and integration tests for their feature
- All feature logic matches official rules and MVP scope

---

# 🔄 Integration & QA

- The Core Trio is responsible for all integration, code review, and system-wide QA.
- Feature Leads focus on delivering their features with minimal dependencies, but must ensure full compliance with official rules and interfaces.
- Regular integration checkpoints ensure smooth merging of isolated features.

---

# 🔥 Global Architecture Rules

- Core owns all contracts, integration, and architectural decisions, and ensures all official rules are enforced.
- Isolated Feature Leads own their feature end-to-end, but must adhere to defined interfaces and all rules for their module.
- All code merges and integration go through the Core Trio.
- All implementation must match the official story, rules, and MVP scope.

---
