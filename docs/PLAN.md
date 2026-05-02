# 🗺️ 4-Week Sprint Plan — Transcendence (Fisher Clash MVP)

This document outlines the official 4-week execution strategy. The project is divided into **5 Vertical Domains**, ensuring all 5 team members have equal, full-stack workloads without stepping on each other's toes.

Goal: Deliver a 100% compliant, 17-point multiplayer game.

---

## 👥 Team Domains (5 Vertical Slices)
- **🟡 Tania (Tech Lead & Dev):** DevOps, Infrastructure & Real-Time Networking.
- **🔵 Samir (Feature Lead):** Database, REST APIs, & Authentication Full-Stack.
- **🟠 Gabriel (PO & Dev):** Core Game Engine & Map UI.
- **🟢 Keillin (PM & Dev):** Combat Logic, Fishing Economy, & Game Mechanics.
- **🔴 Ana Paula (Feature Lead):** Profiles, Social Features & Chat Full-Stack.

*(Note: AI Bots, Action Cards, and Hazards have been removed to ensure the MVP is completed safely within 4 weeks).*

---

## 🟢 WEEK 1 — FOUNDATION & SECURITY
*Goal: Secure the mandatory infrastructure and game engine base.*

- **Tania**: Setup `docker-compose.yml`, HTTPS/TLS certs, and initialize WebSocket server (rejecting unauthenticated users).
- **Samir**: Setup PostgreSQL. Create Users DB Schema. Build Auth REST APIs (bcrypt, JWT) and Mandatory Legal Pages (Privacy, ToS).
- **Gabriel**: Define TypeScript `GameState` models, enums (Phases, Seas). Build the 5-sea Map React UI with mock data.
- **Ana**: Create Friends/Match History DB Schemas. Build the User Profile API and the React Profile UI (visuals).
- **Keillin**: Define the Fishing Loot Tables (Seasons) and Cargo logic in the Game Engine. Build the React Inventory UI.

---

## 🟡 WEEK 2 — SOCIAL & LOBBY
*Goal: Players can log in, chat, and join a room together.*

- **Tania**: Build Lobby backend (Create/Join/Leave Rooms) and Global Chat WebSocket broadcasting.
- **Samir**: Build React Login/Registration UI and setup protected frontend routes.
- **Gabriel**: Implement server-side turn loop and validation. Connect the Map UI clicks to move the player.
- **Ana**: Build the Friends List UI and the Chat UI (connecting to Tania's WebSocket).
- **Keillin**: Build the "Game Customization" Lobby UI (Host selects Map Theme and Game Length).

---

## 🟠 WEEK 3 — FISHER CLASH MECHANICS
*Goal: The game is fully playable with combat and economy.*

- **Tania**: Build Remote Player resilience (save state on disconnect, pause game, allow graceful reconnect).
- **Samir**: Refine Auth/Security edge cases. Assist Tania with Lobby bugs.
- **Gabriel**: Refine Movement logic. Ensure the state machine handles simultaneous connections smoothly.
- **Ana**: Finalize Profile Stats fetching. Add "Online/Offline" status to Friends List.
- **Keillin**: Implement the Pirate Combat logic (dice rolls) and the Market Economy. Implement the "End Game" win screen when the 8-round limit is hit.

---

## 🔴 WEEK 4 — SPECTATOR & POLISH (THE 17 POINTS)
*Goal: Finalize the minor modules and prepare for evaluation.*

- **Tania**: Build Spectator Mode backend (allow 5th connection to join room as viewer).
- **Samir**: Final Docker test. Verify database doesn't crash during simultaneous requests (Multi-user safety).
- **Gabriel**: Final bug-hunting. Ensure illegal moves are rejected server-side without crashing.
- **Ana**: Build Spectator Mode UI (hide move/fish/attack buttons for viewers).
- **Keillin**: Add the "Juice" (Sound effects for fishing/attacking, CSS animations for floating coins).

---

## 🧭 Sprint Rules
1. Never build a feature that is not on the `MODULE_CHECKLIST.md`.
2. Do not start Week 3 until the Week 1 Foundation is 100% merged.
3. If a task takes more than 2 days, ask the team for help immediately.
