# Transcendence: Team Roles & Responsibilities

5 core roles for MVP execution. Small, focused, clear ownership.

---

## 1. 🧠 Game Logic / Backend Lead

**The Brain of the Game**

### Owns:
- Game rules engine (movement, fishing, hazards, card effects)
- Turn system & state transitions
- Win conditions & score calculation
- Game flow (turn phases, action validation)

### Questions they answer:
- "What happens when a player moves to a sea?"
- "How do hazards resolve?"
- "Are these card interactions legal?"
- "Did we hit win condition?"

### Deliverables:
- Game rules/state machine (pseudo-code → real code)
- Turn loop implementation
- Core game mechanics

### Key dependency:
- **Must sync daily with Backend/API/Database dev** — state shape is the contract everything depends on.

---

## 2. 🗄️ Backend / API / Database

**Data, Persistence, System Integration**

### Owns:
- User system (authentication, profiles, session management)
- Database schema (players, matches, game sessions, stats, cards)
- REST/GraphQL API (endpoints for all game actions)
- Game state persistence (save/load, replay support)
- Server infrastructure & configuration

### Questions they answer:
- "Where do we store player data?"
- "What's the API contract between client & server?"
- "How do we handle matchmaking & lobbies?"
- "Does the database scale?"

### Deliverables:
- Auth system (login, registration, tokens)
- Database schema & migrations
- Full API with game action endpoints
- Session/match storage

### Key dependency:
- **Must sync daily with Game Logic dev** — game state shape defines DB schema.

---

## 3. 🌐 Real-Time / Networking / System Architecture

**The Multiplayer Backbone**

### Owns:
- WebSocket/real-time communication layer
- Game room & lobby lifecycle
- Game state synchronization to all clients
- Reconnection handling & edge case resilience
- Latency optimization for multiplayer responsiveness

### Questions they answer:
- "How do we broadcast game events to 6 players?"
- "What happens if a player drops and reconnects?"
- "Is the board in sync across all clients?"
- "Can we handle concurrent player actions?"

### Deliverables:
- WebSocket server (rooms, events, broadcasting)
- State sync protocol (what gets sent when)
- Reconnection flow (rejoin mid-game safely)
- Load handling for multiple concurrent games

### Key dependency:
- Needs **Game Logic to define event types & payload shapes** (turn:begin, player:move, hazard:result, etc.)
- Needs **Frontend to define what state they need to display**

---

## 4. 🎨 Frontend / UI

**Game Experience & Player Interface**

### Owns:
- Board visualization (5 seas, ship positions, resources)
- UI/HUD (cards, action buttons, market, scoreboard)
- Player input handling & validation (before sending to server)
- Basic animations & visual feedback
- Real-time display of server events

### Questions they answer:
- "How does the board look?"
- "Where are my action buttons?"
- "How do I play a card?"
- "Is the board in sync with what the server says?"

### Deliverables:
- Board rendering & ship visualization
- Complete UI mockups & implementation
- Input handling & client-side validation
- Real-time event listeners

### Key dependency:
- **Tight feedback loop with Game Logic dev** — needs to know legal actions before sending.
- Consumes all events from Real-Time/Networking layer.

---

## 5. 🔗 Fullstack Integrator / DevOps / QA

**The Glue That Holds It Together**

### Owns:
- End-to-end integration testing (does a full game actually work?)
- Catching API contract mismatches early
- Deployment pipeline (Docker, staging, production)
- CI/CD setup & automation
- Bug triage & reproduction on real games
- Performance testing & bottleneck identification

### Questions they answer:
- "Does frontend send the right message format for backend?"
- "Did backend break the API contract?"
- "Can we actually play a 5-player game without bugs?"
- "Can we deploy this safely?"

### Deliverables:
- Integration test suite (real game flows)
- Docker/deployment setup
- CI/CD pipeline
- Bug reports & reproduction steps

### Key dependency:
- **Bridges all 4 other roles** — spots integration issues early before they compound.

---

## Communication Pattern

```
Game Logic ←→ Backend/API/DB  (daily sync on state shape)
    ↓            ↓
    └→ Real-Time/Networking ← Frontend
         ↓
    Integrator/QA (monitors all)
```

**Key rule:** When any role ships something that changes the contract (API shape, event format, state structure), notify the Integrator first. They'll catch breaks before they hit production.

---

## MVP Priority Order

1. **Game Logic dev** starts first (define rules & state machine)
2. **Backend/API dev** builds schema & API in parallel
3. **Real-Time dev** integrates WebSocket with API
4. **Frontend dev** starts once API contracts are clear
5. **Integrator/QA dev** runs smoke tests & flags issues

---

## Why This Split Works

- **Clear ownership** — no confusion about who owns what
- **Parallel work** — Game Logic & Backend can start immediately
- **Integration focus** — role #5 catches problems early
- **Scalable** — if you add people later, roles expand naturally
