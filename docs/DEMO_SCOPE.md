# ft_transcendence Demo Scope — 17-Point MVP

This document outlines the minimum features and implementation required for the demo to successfully pass the `ft_transcendence.pdf` evaluation in 4 weeks. 

The goal is to secure exactly **17 points** of modules (providing a 3-point safety buffer) while strictly adhering to all mandatory technical constraints.

---

## 🎯 Demo Goals
- Prove the core technical stack (Next.js/React frontend, Express/Node backend, PostgreSQL database, WebSocket communication).
- Demonstrate 100% compliance with `ft_transcendence` mandatory rules (Docker, HTTPS, True Auth).
- Demonstrate a 4-player multiplayer session with real-time interaction.
- Secure 17 module points so the project can be officially evaluated in Week 4.

---

## 🟢 Must-Have Features for Demo (The 17 Points)

### 1. Mandatory Infrastructure & Auth
- **True Authentication**: Email/password registration and login with bcrypt hashing and JWT. (Nickname-only is an automatic fail).
- **Dockerization**: The entire app launches via `docker-compose up --build`.
- **HTTPS**: Backend and Frontend run over TLS/HTTPS locally.
- **Compliance**: Accessible Privacy Policy and Terms of Service pages.

### 2. Social & User Management
- **User Profiles**: View stats, match history, and upload an avatar.
- **Friend System**: Add/remove friends and see who is currently online.
- **Global Chat**: Real-time chat lobby for all connected users.

### 3. Game Session & Lobby
- **Lobby System**: Create/join game rooms. Display a list of connected players.
- **Game Customization**: Host can select "Map Theme" (Summer/Winter) and "Game Length" (4, 6, or 8 rounds) before starting.
- **Spectator Mode**: Allow users to join a game room as viewers (action buttons hidden).

### 4. Core Game Mechanics (Fisher Clash MVP)
- **Movement (The 6-Sided Dice)**: On your turn, you roll a 6-sided dice to determine your destination:
  - **1, 2, 3, or 4**: Sent to that specific Outer Sea.
  - **5**: Sent to the **Center Lagoon** (Safe Zone / Market).
  - **6**: **Joker!** You choose exactly which of the 5 seas you want to move to.
- **Automatic Battle**: If you land in a Sea already occupied by another player, a **Battle** starts automatically (dice roll; loser drops all fish). The Lagoon is a Safe Zone (no battles allowed).
- **Fishing & Economy**: 
  - **Outer Seas**: High-value fish (Common/Uncommon/Rare).
  - **Lagoon**: Low-value fish or "Trash" (Old Boots worth 0 coins).
  - **Market**: You must be in the Center Lagoon to sell your cargo for coins.
- **Game End Condition**: The game ends automatically based on the Host's "Game Length" setting (4, 6, or 8 rounds). The player with the most coins wins!

### 5. Remote Players & Resilience
- **Remote Play**: Users on 4 different computers can connect via local IP.
- **Reconnection**: Game state is saved. If a player disconnects/closes their browser, the game pauses gracefully until they reconnect.

---

## 🟡 What Can Be Deferred (Post-Evaluation)
*Do NOT build these during the 4-week sprint. They are not required to pass.*
- Bots and AI opponents.
- Full card system and advanced card effects.
- Hazards and environmental damage.
- Complex Combat (e.g., custom weapons, defense cards, sea occupation logic).
- OAuth (42/Google login) and 2FA.
- Complex 3D graphics or heavy animations.

---

## 📝 Implementation Notes
- Focus on stability, clear code structure, and the **Vertical Slice** division of labor.
- All game actions must be validated server-side (no client-side cheating).
- Use WebSocket events for all real-time updates; use REST APIs for standard CRUD operations.
- The project is a Monorepo: share TypeScript interfaces (`GameState`, `User`) between Frontend and Backend.

---

## ✅ Demo Success Criteria (Evaluation Readiness)
- [ ] `docker-compose up` launches the DB, Backend, and Frontend flawlessly over HTTPS.
- [ ] 4 evaluators can register accounts with passwords and log in.
- [ ] Evaluators can add each other as friends and chat in the global lobby.
- [ ] 4 evaluators can join a single game room and play a full match of Fisher Clash.
- [ ] If an evaluator refreshes their page mid-game, they rejoin seamlessly without crashing the server.
- [ ] After the game ends, the winner's stats update on their Profile Page.
