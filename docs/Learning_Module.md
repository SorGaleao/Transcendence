# 🧠 Pre-Project Learning Module (TypeScript + Node.js)

This document defines the **minimum knowledge required** before starting development.

> Goal: Be able to contribute without blocking the team.

---

# 1. 🟦 TypeScript Fundamentals

We use TypeScript (a typed layer over JavaScript).

## Learn:

* Interfaces (like C/C++ structs)
* Enums
* Functions with types
* Arrays & objects
* Basic types (`string`, `number`, etc.)

## Example:

```ts
interface Player {
  id: string;
  hp: number;
  coins: number;
}
```

## Exercise:

1. Extend the `Player` interface:

   * Add `sea: string`
   * Add `inventory: string[]`

2. Create an enum:

```ts
enum Phase {
  PLANNING,
  MOVEMENT,
  ACTION
}
```

3. Add new phases:

* FISHING
* MARKET

---

# 2. ⚡ Async / Await (CRITICAL)

JavaScript is **non-blocking**. This is the biggest shift from C/C++.

## Learn:

* `async` / `await`
* Promises (conceptually)
* Execution order

## Example:

```ts
async function run() {
  const data = await getData();
  console.log(data);
}
```

## Exercise:

1. Write a function:

```ts
function getData(): Promise<string>
```

2. Simulate delay using:

```ts
setTimeout
```

3. Log:

* "Start"
* result of `getData()`
* "End"

👉 Observe the order of execution.

4. Remove `await` and run again.
   👉 What changes?

---

# 3. 🧩 Node.js Runtime

Node.js runs your backend.

## Learn:

* What Node.js is
* How to run a file
* Module system (`import/export`)

## Exercise:

1. Create file:

```
index.ts
```

2. Add:

```ts
console.log("Game server starting...");
```

3. Run it using Node.

---

# 4. 📦 npm (Package Manager)

npm manages dependencies and scripts.

## Learn:

* `package.json`
* Installing dependencies
* Running scripts

## Exercise:

1. Initialize project:

```bash
npm init -y
```

2. Install TypeScript:

```bash
npm install typescript
```

3. Add script in `package.json`:

```json
"scripts": {
  "dev": "ts-node index.ts"
}
```

4. Run:

```bash
npm run dev
```

---

# 5. 🌐 Event-Driven Thinking

Your game is **event-based**, not linear.

## Learn:

* Code runs on events
* Message-based systems
* Basic WebSocket idea

## Example Event:

```ts
type GameEvent = {
  type: string;
  payload: any;
};
```

## Exercise:

1. Create event:

```ts
const moveEvent = {
  type: "PLAYER_MOVE",
  payload: { playerId: "p1", sea: "SEA_2" }
};
```

2. Create a function:

```ts
function handleEvent(event: GameEvent)
```

3. Inside:

* Log different messages based on `event.type`

---

# 6. 🗄️ Database Basics

We store players and sessions.

## Learn:

* Tables / collections
* Rows / documents
* IDs
* Insert & query

## Exercise:

1. Design a table (on paper or text):

### Players:

* id
* coins
* hp
* sea

### Sessions:

* id
* createdAt

2. Answer:

* What identifies a player uniquely?
* What links a player to a session?

---

# 7. 🧠 Game Architecture Basics

Everyone must understand core concepts.

## Learn:

* GameState
* Turn system
* Phases
* Events

## Example:

```ts
interface GameState {
  turn: number;
  phase: string;
  players: Player[];
}
```

## Exercise:

1. Add to GameState:

* current phase (enum)
* list of players
* current turn

2. Simulate:

* Turn 1 → Player moves
* Turn 2 → Player fishes

👉 Update GameState manually.

---

# ⏱ Recommended Time

* TypeScript → 2–3h
* Async/Await → 2h
* Node + npm → 1h
* Events & Sockets → 2h
* React & Prisma → 5-6h

Total: ~12–15 hours

---

# ✅ Ready Checklist

Before starting, you should be able to:

* Write basic TypeScript types
* Use async/await correctly
* Run the project with npm
* Understand event-driven flow
* Understand GameState concept

---

# ⚠️ Important

Do NOT overlearn:

* Advanced TypeScript
* Complex design patterns
* Things not required by the 17-point scope

👉 Learn just enough to start building.

---

# 🚀 Final Rule

> If you don’t understand something, build a small example and test it.

Learning happens through execution, not theory.

---

EXTRA:

---

### # 8. 🌐 REST APIs with Express.js 
*You know how HTTP works from `webserv`. Express just makes it 100x easier.*
**Learn:**
*   Initializing an Express app.
*   Handling `app.get()` and `app.post()`.
*   Reading JSON from `req.body`.

**Exercise:**
1. Create a simple Express server:
```ts
import express from 'express';
const app = express();
app.use(express.json());

app.post('/login', (req, res) => {
  const { email, password } = req.body;
  res.json({ message: "Login successful!", token: "12345" });
});

app.listen(3000, () => console.log("Server running on port 3000"));
```
2. Test it using `curl` or Postman.

---

### # 9. 🎨 Frontend UI with React / Next.js
*How to build the visual interface that users interact with.*
**Learn:**
*   **Components**: Functions that return HTML (JSX).
*   **Props**: Passing data from a parent component to a child component.
*   **State (`useState`)**: Making the UI update when a variable changes.

**Exercise:**
1. Create a simple React Counter Component:
```tsx
import { useState } from 'react';

export default function Counter() {
  const [coins, setCoins] = useState(0);

  return (
    <div>
      <h1>Player Coins: {coins}</h1>
      <button onClick={() => setCoins(coins + 1)}>
        Fish for Coins!
      </button>
    </div>
  );
}
```
2. Click the button and watch the screen update automatically (no DOM manipulation required!).

---

### # 10. 🗄️ Database ORM with Prisma
*How to talk to PostgreSQL using TypeScript instead of raw SQL queries.*
**Learn:**
*   What an ORM (Object-Relational Mapper) is.
*   How to write a `schema.prisma` file.

**Exercise:**
1. Look at this Prisma schema:
```prisma
model User {
  id       Int      @id @default(autoincrement())
  email    String   @unique
  username String
  password String
}
```
2. Understand that Prisma will automatically generate a TypeScript function for you called `prisma.user.create({ data: { email, username, password } })`.

---