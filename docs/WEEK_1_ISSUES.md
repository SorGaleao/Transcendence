# 🟢 WEEK 1 — FINAL ISSUE SET (DOMAIN-BASED)

*Note: Do not put team member names in the issue titles or descriptions. Use GitHub's "Assignees" feature to assign them. If a team member changes, the issue remains the same.*

### 🛠️ DOMAIN: DEVOPS & NETWORKING
*Focus: Containers and real-time pipes.*
- **Issue 1** — Setup `docker-compose.yml`
  - Containerize Frontend, Backend, and PostgreSQL database
- **Issue 2** — Setup HTTPS/TLS certificates
  - Generate local certs for backend and frontend (Mandatory requirement)
- **Issue 3** — Setup WebSocket server base
  - Create server; handle client connect/disconnect
  - **Crucial**: Reject connections that do not have a valid Auth Token
- **Issue 4** — Create event message format system
  - Standardize real-time event structure (type, payload, timestamp)

### 🔵 DOMAIN: SECURITY & DATABASE
*Focus: Database connection and mandatory authentication.*
- **Issue 5** — Setup database connection
  - Connect DB; setup ORM (Prisma/TypeORM)
- **Issue 6** — Create Users DB schema
  - Define `Users` table (id, email, username, password_hash)
- **Issue 7** — Implement Backend Auth APIs
  - Build Registration & Login REST endpoints (bcrypt hashing, JWT generation)
- **Issue 8** — Create Mandatory Legal Pages
  - Build `Privacy Policy` and `Terms of Service` React screens (Mandatory requirement)

### 🟠 DOMAIN: CORE ENGINE & MAP UI
*Focus: The board and the turn rules.*
- **Issue 9** — Create GameState base model
  - Define player structure (HP, coins, sea, inventory)
- **Issue 10** — Define core enums & constants
  - Game phases, Sea IDs (1 Center Lagoon, 4 Outer Seas)
- **Issue 11** — Implement server-side turn counter system
  - Create turn index; Increment turn each cycle
- **Issue 12** — Create 5-sea map layout UI
  - Render center + 4 outer seas; basic CSS/styling
- **Issue 13** — Create player rendering system
  - Show player icons on map; bind to mock GameState data

### 🟢 DOMAIN: ECONOMY & MECHANICS
*Focus: Rules of the economy and the inventory.*
- **Issue 14** — Define the Fishing Loot Tables
  - Create TypeScript objects mapping fish rarity to the Season (Summer/Winter)
- **Issue 15** — Implement Cargo limit logic
  - Create the function to enforce the 3-fish maximum and reject actions if full
- **Issue 16** — Build the player Inventory React UI
  - Create the visual panel that shows the player's current coins and 3 cargo slots

### 🔴 DOMAIN: PROFILES & SOCIAL
*Focus: User-experience UI and profile APIs.*
- **Issue 17** — Create Friends & Match History DB schemas
  - Define `Friends` table and `Matches` table in the ORM
- **Issue 18** — Implement basic User Profile API
  - Build REST endpoint to fetch user data (username, basic stats)
- **Issue 19** — Create basic User Profile UI
  - Build profile screen; fetch data from Issue 18 endpoint
- **Issue 20** — Create Friends List UI
  - Build list component (visuals and mock data for now)
- **Issue 21** — Create Global Chat UI
  - Build chat window component (visuals and mock data for now)

---

### 🗑️ GITHUB CLEANUP INSTRUCTIONS (For Keillin)
Since Keillin already created Issues #1 to #25 three weeks ago, she should:
1. **Close/Delete** any old issues related to `Bots + Hazard` (e.g., Old Issues 21, 22, 23, 25).
2. **Rename/Edit** the existing issues to match this new 21-Issue list perfectly.
3. Use GitHub's **"Assignees"** button on the right sidebar to assign the 5 team members to their respective Domains. 
