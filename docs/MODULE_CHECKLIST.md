# 🎯 FT_Transcendence 17-Point Evaluation Checklist

Checklist designed to be used directly during evaluation. It maps your "Fisher Clash" MVP directly to the official `ft_transcendence` grading sheet.
Minimum of 14 points to approve.

---

## 🛑 1. Mandatory General Requirements 
- [ ] **Dockerization**: Deploys via a single `docker-compose up --build`.
- [ ] **Database**: PostgreSQL with a clear schema (Users, Sessions, Matches).
- [ ] **Security**: Passwords are hashed using `bcrypt` (No plain text, no nickname-only login).
- [ ] **HTTPS**: Backend and Frontend are served over TLS/HTTPS locally.
- [ ] **Compliance**: Real, accessible `Privacy Policy` and `Terms of Service` pages.
- [ ] **Cross-Browser**: Works perfectly on the latest Google Chrome.
- [ ] **Multi-User Safety**: Game logic and DB do not crash with simultaneous inputs.

---

## 🌟 2. Major Modules (2 Points Each) - 14 Points Total

- [ ] **Major 1: Web Frameworks (2 pts)**
  - *Requirement*: Use a framework for frontend and backend.
  - *Our Implementation*: Next.js/React (Frontend) and Node.js/Express (Backend).

- [ ] **Major 2: Real-Time Features (2 pts)**
  - *Requirement*: WebSockets for real-time updates across clients.
  - *Our Implementation*: Real-time game state broadcasting, Lobby tracking, and Chat via `Socket.io`.

- [ ] **Major 3: Allow Users to Interact (2 pts)**
  - *Requirement*: Basic chat, profile system, and friends system.
  - *Our Implementation*: Global chat lobby, User Profiles, and adding/removing friends.

- [ ] **Major 4: Standard User Management (2 pts)**
  - *Requirement*: Update profile, upload avatar, see friends online status.
  - *Our Implementation*: Avatar upload, Profile UI, and tracking online/offline status in the Friends List.

- [ ] **Major 5: Web-Based Game (2 pts)**
  - *Requirement*: Playable live matches against each other.
  - *Our Implementation*: "Fisher Clash" (Moving between 5 seas, fishing, and simple combat).

- [ ] **Major 6: Multiplayer 3+ (2 pts)**
  - *Requirement*: Support for three or more players simultaneously.
  - *Our Implementation*: The game requires exactly 4 players in a room to start.

- [ ] **Major 7: Remote Players (2 pts)**
  - *Requirement*: Play on separate computers, handle disconnections, reconnection logic.
  - *Our Implementation*: Playable via local IP; if a player closes their browser, the game state is saved, and they can reconnect seamlessly.

---

## ⭐ 3. Minor Modules (1 Point Each) - 3 Points Total

- [ ] **Minor 1: Game Customization Options (1 pt)**
  - *Requirement*: Different maps or themes. Customizable game settings.
  - *Our Implementation*: Two dropdowns in the Lobby. 1) **Map Theme**: "Floripa Seasons" (changes CSS background and fish loot table). 2) **Game Length**: "4, 6, or 8 Rounds" (changes mechanical length of the game). This double-customization 100% guarantees the point.

- [ ] **Minor 2: Spectator Mode (1 pt)**
  - *Requirement*: Allow users to watch ongoing games in real-time.
  - *Our Implementation*: A 5th player can join a game room. Their action buttons are hidden, but they receive live WebSocket board updates.

- [ ] **Minor 3: Game Statistics & Match History (1 pt)**
  - *Requirement*: Track wins/losses, display match history.
  - *Our Implementation*: A `match_history` table in the DB. The User Profile displays total wins and a list of past matches.

---

### Total Score: 17 / 14 Points (Safety Buffer: 3 Points)
