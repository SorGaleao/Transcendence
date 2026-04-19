# 🗺️ Alternative Project Plan — Transcendence (Five Seas: Fisher Clash)

This plan adapts the 4-week execution strategy to the alternative team structure:
- **Core (Gab, Tania, Keillin):** Own all integration-heavy, architectural, and cross-feature work (core engine, networking, database, contracts, reviews, deployment, and at least one major feature).
- **Feature Leads (Ana Paula, Samir):** Each owns a self-contained feature (e.g., bots/hazards, fishing/economy, or another module), including backend, frontend, and testing for their slice.

Goal:
👉 Deliver a playable multiplayer game in 4 weeks (Quick Mode first), then extend if time allows.

---


# 🧠 Global Strategy

- Week 1 → Foundation (game runs, even if minimal)
- Week 2 → Full gameplay loop (end-to-end match playable)
- Week 3 → Features + balancing (game becomes fun)
- Week 4 → Polish + stabilization + demo prep

**All implementation must follow the official rules:**
- 6-phase turn structure (Trading/Market, Action Cards, Movement/Battles, Mandatory Fishing, Reward/Consequence Cards, Emergency Sale)
- 5-sea map with occupancy and battle rules
- Server-authoritative logic and event-driven architecture (WebSocket events)
- Reconnection and state recovery
- Cargo limits, set collection, and tiebreakers
- MVP scope: lobby, movement, combat, hazards, fishing, fish selling, basic cards, endgame ranking

---

# 👥 Team Roles Summary (Alternative)

- 🧠 Core Trio (Gab, Tania, Keillin) → Core Engine, Networking, Database, Integration, Reviews, Major Feature
- 🏝️ Ana Paula → Isolated Feature Lead (e.g., Bots/Hazards)
- 🏝️ Samir → Isolated Feature Lead (e.g., Fishing/Economy)

---

# 🟢 WEEK 1 — FOUNDATION

## 🎯 Goal:
A multiplayer session can start and players can move in a basic loop.

---

## 🧠 Core Trio
- Define GameState structure and all data contracts (player state, seas, events, cards, cargo, coins, HP)
- Implement turn system skeleton and 6-phase turn flow
- Setup WebSocket server and lobby system
- Create room/session handling and event system structure (e.g., lobby:update, turn:begin, player:move, combat:start, hazard:result, fishing:result, market:sell, card:played, player:sunk, game:end)
- Setup database (initial schema: players, sessions, game state snapshot, match history, statistics)
- Implement minimal persistence layer and reconnection/state recovery
- Review and integrate isolated feature API contracts
- Ensure all MVP rules are enforced server-side

---

## 🏝️ Isolated Feature Leads
- Define feature structure and data models (e.g., bot logic, hazard system, fishing, economy, cards)
- Implement all rules-driven requirements for their feature:
	- For fishing/economy: cargo limits, fish rarity, set bonuses, emergency sale, market, card effects
	- For bots/hazards: bot AI, hazard resolution, environmental damage, event triggers
- Create UI placeholders for their feature
- Implement basic backend logic (placeholders)
- Prepare integration tests for their module

---

# 🟡 WEEK 2 — CORE GAME LOOP

## 🎯 Goal:
Full playable match loop exists end-to-end.

---

## 🧠 Core Trio
- Implement full turn cycle and rule validation (all 6 phases)
- Full event system implementation (WebSocket)
- Turn synchronization and session persistence
- Save/load game state in database
- Reconnection system (basic)
- Integrate isolated features via defined APIs
- Ensure MVP scope is met: movement, combat, hazards, fishing, fish selling, cards, endgame ranking

---

## 🏝️ Isolated Feature Leads
- Implement main feature logic (e.g., bot AI v1, hazard system, fishing, economy, card effects)
- UI integration for their feature
- Ensure all feature logic matches official rules (e.g., cargo, set collection, card timing, hazard tables)
- Run integration tests with core systems

---

# 🟠 WEEK 3 — FEATURES + BALANCING

## 🎯 Goal:
Game becomes interesting, balanced, and visually clear.

---

## 🧠 Core Trio
- Balance risk/reward system (as per rules)
- Optimize game state handling and server performance
- Improve reconnection and database stability
- Review and merge isolated feature improvements
- Implement and track match statistics/metrics (coins, fish caught, sets, damage, win rate, etc.)

---

## 🏝️ Isolated Feature Leads
- Improve feature logic (smarter bots, more hazards, richer fishing/economy, card effects)
- Add UI/UX polish for their module
- Continuous integration testing

---

# 🔴 WEEK 4 — POLISH + DEMO PREP

## 🎯 Goal:
Stable, clean, demo-ready game.

---

## 🧠 Core Trio
- Final bug fixes and rule lock
- Server and database stability
- Final integration and demo prep
- Code review and documentation

---

## 🏝️ Isolated Feature Leads
- Final polish and bug fixes for their feature
- Demo rehearsal and feedback
- Ensure seamless integration with core systems

---

# 🧭 Final Rules (Alternative)

- Core Trio owns all contracts, integration, and architectural decisions, and ensures all official rules are enforced.
- Isolated Feature Leads own their feature end-to-end, but must adhere to defined interfaces and all rules for their module.
- All code merges and integration go through the Core Trio.
- If a feature is not required for a full match → cut it.
- Week 4 is strictly for polish and bug fixing.
- Bots must use the same system as real players.
- All implementation must match the official story, rules, and MVP scope.

---

# 🏁 Final Outcome

- Week 1 → system exists  
- Week 2 → game is fully playable  
- Week 3 → game is fun and balanced  
- Week 4 → game is demo-ready and stable  

---
