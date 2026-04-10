# 🗺️ Transcendence Project Plan  
## Five Seas: Fisher Clash

This document defines the 4-week execution plan split per team member.

Goal:
👉 Deliver a playable multiplayer game in 4 weeks (Quick Mode first), then extend if time allows.

---

# 🧠 Global Strategy

- Week 1 → Foundation (game runs, even if minimal)
- Week 2 → Full gameplay loop (end-to-end match playable)
- Week 3 → Features + balancing (game becomes fun)
- Week 4 → Polish + stabilization + demo prep

---

# 👥 Team Roles Summary

- 🧠 Samir → Core Engine & Game Rules  
- 🌐 Tania → Networking + Database + Sessions  
- 🎮 Gabriel → Movement + Map + Player UI  
- 💰 Keillin → Fishing + Economy + UI  
- 🤖 Ana Paula → Bots + Hazards + Integration + QA  

---

# 🟢 WEEK 1 — FOUNDATION (Make it run)

## 🎯 Goal:
A multiplayer session can start and players can move in a basic loop.

---

## 🧠 Samir — Core Engine
- Define GameState structure
- Implement turn system skeleton
- Implement phase system (empty logic)
- Define all data contracts (players, seas, events)
- Create rule interface (movement/fishing placeholders)

---

## 🌐 Tania — Networking + Database
- Setup WebSocket server
- Create lobby system (join/leave/start game)
- Create room/session handling
- Define event system structure
- Setup database (initial schema)
  - players
  - sessions
  - game state snapshot (basic)
- Implement minimal persistence layer

---

## 🎮 Gabriel — Movement + Map
- Create basic map UI (5 seas)
- Render players on map
- Implement movement UI (send intent only)
- Connect to server events (movement placeholder)

---

## 💰 Keillin — Fishing + Economy
- Define fish types + rarity structure
- Create inventory data model
- Create UI placeholders (inventory/market)
- No real logic yet (structure only)

---

## 🤖 Ana Paula — Bots + Hazards + QA
- Setup logging system (turn/event logs)
- Create bot simulation (random actions placeholder)
- Setup QA testing environment (manual match testing flow)
- Define hazard system structure (no logic yet)

---

## 🧪 Week 1 Milestone:
👉 Players can join lobby and move in a shared session (even if fake logic)

---

# 🟡 WEEK 2 — CORE GAME LOOP

## 🎯 Goal:
Full playable match loop exists end-to-end.

---

## 🧠 Samir — Core Engine
- Implement full turn cycle
- Implement movement validation rules
- Implement fishing resolution logic
- Implement hazard hooks (called but simple)
- Integrate with server events

---

## 🌐 Tania — Networking + Database
- Full event system implementation (WebSocket)
- Turn synchronization system
- Save/load game state in database
- Reconnection system (basic state restore)
- Session persistence improvements

---

## 🎮 Gabriel — Movement + Map
- Full movement system integration
- Sea occupancy logic (Quick Mode)
- Visual feedback for movement and position updates

---

## 💰 Keillin — Fishing + Economy
- Implement fishing logic per sea
- Implement selling system
- Coins system
- Basic market interaction

---

## 🤖 Ana Paula — Bots + Hazards + QA
- Implement bot AI v1 (basic decision-making)
- Implement hazard system (basic damage/events)
- Run full match simulations with bots
- Identify sync and logic issues

---

## 🧪 Week 2 Milestone:
👉 A full match can be played end-to-end with bots filling missing players

---

# 🟠 WEEK 3 — FEATURES + BALANCING

## 🎯 Goal:
Game becomes interesting, balanced, and visually clear.

---

## 🧠 Samir — Core Engine
- Balance risk/reward system
- Improve turn resolution clarity
- Add hooks for future features (cards if needed)
- Optimize game state handling

---

## 🌐 Tania — Networking + Database
- Optimize WebSocket performance
- Improve reconnection stability
- Database optimization (snapshots/history)
- Reduce desync issues

---

## 🎮 Gabriel — Movement + Map
- Improve UI clarity (animations, highlights)
- Add sea danger visualization
- Improve player feedback

---

## 💰 Keillin — Fishing + Economy
- Add set collection system
- Balance fish rarity and rewards
- Improve market UI/UX
- Add bonus calculations

---

## 🤖 Ana Paula — Bots + Hazards + QA
- Improve bot AI (smarter decisions)
- Expand hazard variety (storms, monsters, etc.)
- Continuous full-match testing
- Cross-system bug fixing

---

## 🧪 Week 3 Milestone:
👉 Game is fun, stable, and strategically meaningful

---

# 🔴 WEEK 4 — POLISH + DEMO PREP

## 🎯 Goal:
Stable, clean, demo-ready game.

---

## 🧠 Samir — Core Engine
- Final bug fixes
- Lock game rules (no major changes)
- Ensure deterministic behavior

---

## 🌐 Tania — Networking + Database
- Final server stability improvements
- Fix sync edge cases
- Ensure DB consistency for demo
- Prevent session crashes

---

## 🎮 Gabriel — Movement + Map
- UI polish
- Fix rendering issues
- Improve responsiveness

---

## 💰 Keillin — Fishing + Economy
- UI polish
- Final balance tweaks
- Improve feedback clarity

---

## 🤖 Ana Paula — Bots + Hazards + QA
- Full system QA (daily full matches required)
- Crash prevention testing
- Demo rehearsal simulation
- Final integration validation

---

## 🧪 Week 4 Milestone:
👉 Fully playable, stable multiplayer demo with bots ensuring full matches always work

---

# 🧭 Final Rules

## 🚨 MVP Priority Rule:
If a feature is not required for a full match → cut it.

---

## ⚖️ Stability Rule:
Week 4 is strictly for polish and bug fixing.

---

## 🤝 Integration Rule:
Bots must use the same system as real players.

---

# 🏁 Final Outcome

- Week 1 → system exists  
- Week 2 → game is fully playable  
- Week 3 → game is fun and balanced  
- Week 4 → game is demo-ready and stable  

---