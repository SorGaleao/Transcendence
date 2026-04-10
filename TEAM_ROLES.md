# 👥 Team Structure — Transcendence Project (Five Seas: Fisher Clash)

This document defines the responsibilities of each team member to ensure parallel development, clear ownership, and smooth integration.

The architecture is designed around:
- A shared **Core Game Engine**
- A centralized **Networking + Database layer**
- Feature-based full-stack ownership
- Early integration with **bot players for testing**

---

# 🧠 1. Core Engine & Tech Lead (Samir)

## Ownership
- Game state model (single source of truth)
- Turn system & phase resolution
- Core game rules (movement, fishing, economy rules, hazards logic if needed)
- Deterministic game logic (no side effects, no I/O)

## Responsibilities
- Define and maintain all game data contracts:
  - Player state structure
  - Game state structure
  - Event types and payloads
- Ensure consistency of game rules across all systems
- Review all rule-related pull requests

## Constraints
- ❌ Does NOT build UI
- ❌ Does NOT manage database or networking

## Deliverables
- Core game engine (pure logic layer)
- Turn loop implementation
- Rule resolution system

---

# 🌐 2. Networking, Database & Game Session Lead (Person B)

## Ownership
- WebSocket server (real-time communication)
- Lobby system (create / join / start game)
- Game session lifecycle (start → end)
- Event system (server-authoritative architecture)
- Database (single source of truth for persistence)

---

## Database Responsibility (CRITICAL)
Person B is the **only owner of database schema and persistence logic**.

The database stores:
- Players
- Game sessions
- Match history
- Reconnection state

Other team members may request data needs but do not define schema.

---

## Responsibilities
- Implement WebSocket server and event routing
- Manage game sessions and rooms
- Ensure server-authoritative gameplay
- Handle player reconnection and state recovery
- Implement persistence layer (DB or lightweight storage)

## Deliverables
- WebSocket infrastructure
- Lobby and session system
- Event system (`turn:begin`, `player:move`, etc.)
- Database schema and persistence layer
- Reconnection system

---

# 🎮 3. Movement, Map & Player State Lead (Person C)

## Ownership
- Movement system (validated through Core Engine)
- Sea occupancy logic (quick and full mode support)
- Player positioning system

## Frontend Responsibilities
- Map UI (5 seas visualization)
- Player position rendering
- Movement controls and interactions

## Backend Responsibilities
- Movement request handling (via server events)
- State updates via Core Engine + Networking layer

## Constraints
- ❌ Does NOT define database schema
- ✔ Requests required data fields from Networking Lead

## Deliverables
- Movement system implementation
- Map UI
- Player state integration

---

# 💰 4. Fishing, Economy & UI Lead (Person D)

## Ownership
- Fishing system (core logic via Core Engine)
- Economy system (coins, selling, sets)
- Inventory system (fish storage)

## Frontend Responsibilities
- Inventory UI
- Market UI
- Fishing results display
- Transaction feedback UI

## Backend Responsibilities
- Fishing result processing
- Economy calculations (selling, bonuses, sets)

## Constraints
- ❌ Does NOT define database schema
- ✔ Requests required persistence needs from Networking Lead

## Deliverables
- Fishing system
- Economy system
- Inventory + market UI
- Integration with game events

---

# 🤖 5. Bots, Hazards & Integration Lead (Person E)

## Ownership
- Bot AI system (simulated players)
- Hazard system (storms, damage events, environmental effects)
- Game balancing support (risk tuning and gameplay feel)

## Frontend Responsibilities
- Turn/event logs
- Damage and hazard feedback UI
- Bot indicators (optional visualization)

---

## Integration & QA Responsibility (CRITICAL)
Person E is responsible for:
- Running full game simulations daily
- Testing full matches (6–8 players with bots)
- Validating system integration across all modules
- Ensuring stability of full gameplay loop

## Deliverables
- Bot AI system
- Hazard system
- Integration testing suite
- Game balancing support tools
- UI feedback for events and damage

---

# 🔥 Global Architecture Rules

## 🧠 Core Engine is authoritative
All game rules must be resolved by the Core Engine.

---

## 🌐 Server is the source of truth
All actions are validated and processed server-side.

Clients only send **intent**, never results.

---

## 🗄️ Database ownership is centralized
Only Networking Lead (Person B) defines and manages:
- Schema
- Persistence
- Storage logic

---

## 🤝 Feature-based full-stack ownership
Each team member owns a feature end-to-end (backend + frontend + integration).

---

## 🧪 Bots simulate real players
Bots must use the same API and event system as human players.

---

# 🚀 Design Goal

This structure is designed to:
- Enable parallel development from day 1
- Avoid frontend/backend bottlenecks
- Ensure early multiplayer testing
- Guarantee a playable demo through bot integration
- Minimize integration risk before evaluation

---