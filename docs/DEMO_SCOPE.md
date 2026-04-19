# ft_transcendence Demo Scope — Minimal Viable Product

This document outlines the minimum features and implementation required for the demo to satisfy the ft_transcendence.pdf requirements. The goal is to deliver a functional, testable, and presentable demo within the 4-week plan. The full game and advanced features can be completed after this milestone.

---

## 🎯 Demo Goals
- Prove the core technical stack (Node.js/TypeScript backend, React frontend, PostgreSQL database, WebSocket communication)
- Demonstrate multiplayer session with real-time interaction
- Show basic game loop and player actions
- Validate integration, persistence, and reconnection

---

## 🟢 Must-Have Features for Demo

### 1. User Authentication & Lobby
- Simple login (can be nickname-based, no full auth required)
- Lobby system: create/join game room
- Display list of connected players

### 2. Game Session & Turn System
- Start game with 2+ players (bots can fill empty seats)
- Server-authoritative turn system (players take turns in order)
- Basic turn timer (optional, but recommended)

### 3. Map & Movement
- Visualize 5-sea map (lagoon + 4 outer seas)
- Players can move their ship to a sea (enforce occupancy rule)
- Basic movement validation (no battle logic required for MVP)

### 4. Fishing & Economy
- Each player can "fish" once per turn (random fish assigned)
- Cargo limit enforced (e.g., 4 fish slots)
- Fish can be sold in the lagoon for coins
- Display player inventory and coin count

### 5. Basic Bot Support
- Bots fill empty seats and take random valid actions

### 6. Persistence & Reconnection
- Game state is saved in the database
- Players can disconnect/reconnect and resume their session

### 7. Minimal UI
- Lobby screen
- Game board with player positions
- Inventory and coin display
- Basic action buttons (move, fish, sell)

---

## 🟡 What Can Be Deferred (Post-Demo)
- Full card system and advanced card effects
- Hazards and environmental damage
- Combat/battle system for sea occupation
- Advanced bot AI
- Set collection bonuses
- Market bonuses and emergency sale
- Full statistics and match history
- Spectator mode
- Polished UI/UX and animations
- Full authentication and user profiles

---

## 📝 Implementation Notes
- Focus on stability, clear code structure, and integration
- All actions must be validated server-side (no client-side cheating)
- Use WebSocket events for all real-time updates
- Keep the codebase modular to allow easy extension after the demo

---

## ✅ Demo Success Criteria
- Multiple users can join a lobby and start a game
- Players can move, fish, and sell fish for coins
- Game state persists and recovers after disconnect
- All actions are reflected in real time for all players
- The demo is playable, stable, and demonstrates the core architecture

---

This scope ensures you meet the ft_transcendence.pdf requirements for the demo milestone. After this, you can extend to the full game with all advanced features and polish.
