# 👥 Team Roles — Transcendence Project (Fisher Clash MVP)

The project is divided into **5 Vertical Domains**. Every team member works Full-Stack within their domain to prevent bottlenecks and ensure everyone learns React, Node.js, and Database interaction.

---

## 🟡 Tania (Tech Lead) — DevOps & Networking

**Ownership**
- Infrastructure, Deployment, and Security protocols.
- Real-Time WebSocket communication.

**Responsibilities**
- Containerize the application using Docker.
- Setup and enforce HTTPS/TLS connections locally.
- Build the `Socket.io` gateway and handle the connection lifecycle (connect/disconnect/reconnect).
- Ensure WebSockets explicitly reject unauthenticated connections.

**Deliverables**
- `docker-compose.yml`
- Global Chat backend broadcasting system.
- Lobby Room management (Create/Join rooms).
- Remote Player resilience (state recovery on disconnect).
- Spectator Mode backend logic.

---

## 🔵 Samir (Feature Lead) — Security & Database

**Ownership**
- PostgreSQL configuration and the central Authentication REST APIs.

**Responsibilities**
- Configure Prisma/TypeORM and set up the primary `Users` table.
- Implement the JWT token generation and bcrypt password hashing.
- Build the React Login/Registration screens.
- Build the mandatory legal compliance pages.

**Deliverables**
- PostgreSQL database instance.
- Authentication REST API endpoints.
- Login and Registration UI.
- Privacy Policy and Terms of Service UI.

---

## 🟠 Gabriel (PO & Dev) — Core Game Engine & Map UI

**Ownership**
- The foundational server-side rules of the game and the visual game board.

**Responsibilities**
- Architect the TypeScript `GameState` models and share them between frontend and backend.
- Build the server-side turn loop and movement validation.
- Ensure illegal moves are rejected server-side without crashing.
- Build the React Map UI that visualizes the 5 Seas.

**Deliverables**
- Monorepo shared `packages/game-engine` data structures.
- Turn counter and Phase state machine.
- 5-Sea Map UI with interactive click-to-move.
- Real-time rendering of player positions on the map.

---

## 🟢 Keillin (PM & Dev) — Game Mechanics & Economy

**Ownership**
- The math, rules, and economy of Fisher Clash, plus UI polish.

**Responsibilities**
- Write the Fishing RNG logic and Loot Table configurations.
- Implement Pirate Combat dice rolls and the Lagoon "Safe Zone" rules.
- Write the logic that enforces the 3-fish cargo limit.
- Manage the GitHub project board and ensure tasks are tracking well.

**Deliverables**
- Fishing API and Combat API logic inside the Game Engine.
- Game Customization Lobby UI (Length / Map Theme selection).
- Player Inventory React UI.
- "End Game" win screen when the round limit hits.
- Game Juice (Sound effects, CSS floating coin animations).

---

## 🔴 Ana Paula (Feature Lead) — Social & Profiles

**Ownership**
- The entire social experience of the platform.

**Responsibilities**
- Design the Database schemas for `Friends` and `Match History`.
- Build the REST APIs to fetch player stats and match records.
- Build the React components for the Chat and Friends list.
- Track "Online/Offline" status using WebSockets.

**Deliverables**
- User Profile Page UI (Avatar, Stats, History).
- Global Chat Window UI.
- Friends List UI (Add/Remove friends).
- Spectator Mode UI (View-only Map).

---

# 🔄 Integration & QA Rules
1. **The Golden Rule**: Never wait for someone else's backend. Use "Mock Data" (fake hardcoded variables) to build your React UI until their API is ready.
2. **Merge Conflict Avoidance**: Because everyone owns a separate Vertical Domain, you will rarely touch the same files.
3. **The 48-Hour PM Rule**: If a developer is stuck on a critical task for more than 48 hours, Keillin (PM) must immediately re-assign someone (like Gabriel) to pair-program and unblock them.
