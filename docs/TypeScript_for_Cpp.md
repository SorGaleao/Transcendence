# TypeScript for C/C++ Developers

This document explains, in practical detail, how to work with TypeScript if you come from a C/C++ background. It maps common concepts, provides code examples and highlights common pitfalls.

---

## 1. Quick overview

- TypeScript (TS) is a superset of JavaScript that adds optional static typing. TS code compiles to JavaScript and runs on JS runtimes (Node, browsers).
- TypeScript performs compile-time type checking; types do not exist at runtime (except `enum`, which generates a JS object).

---

## 2. Type mappings and variables

- C++: `int`, `float`, `double`, `long`, `unsigned`, etc.
- TS: `number` (single type for integers and floats), `bigint` (for large integers), `string`, `boolean`.

Examples:

```ts
// TypeScript
const a: number = 10; // floating/integers are represented by `number`
const b: bigint = 9007199254740991n;
const s: string = "text";
```

Key difference: there is no pointer arithmetic or manual memory control in TS.

Syntax:

name_var: Type = value;
a: number = 10; //specify type to the system

or

let name_var = value;
let a = 10; //system finds type alone

Both cases works normally;
---

## 3. Variable declarations: `const`, `let`, `var`

- Use `const` by default for values that should not be reassigned.
- Use `let` for mutable variables.
- Avoid `var` — it has function scoping and hoisting semantics that lead to bugs.

Example:

```ts
const PI = 3.14;
let counter = 0;
```

Detailed explanation for `let`:

- `let` is block-scoped (like a variable declared inside `{}` in C++ block). It does not allow redeclaration in the same scope.
- `let` is not hoisted in the same way as `var`: it is subject to the Temporal Dead Zone (TDZ). Accessing a `let` variable before its declaration throws a ReferenceError.
- Use `let` when you need to mutate a variable across statements or loops, e.g. counters, temporary accumulators.

Examples showing `let` behavior:

```ts
if (true) {
  let x = 10;
  // x is available only inside this block
}

// Temporal Dead Zone example
{
  // console.log(y); // ReferenceError: Cannot access 'y' before initialization
  let y = 5;
}
```

`let` vs `var` quick note:

```ts
function demo() {
  if (true) {
    var v = 1; // function-scoped
    let l = 2; // block-scoped
  }
  console.log(v); // 1
  // console.log(l); // ReferenceError
}
```

---

## 4. `const` — reassignment vs deep immutability

In C++ `const` often indicates immutability (no modification to the object or value). In JavaScript/TypeScript, `const` means the variable binding cannot be reassigned, but the value it references may still be mutable if it is an object or array.

Examples:

```ts
const obj = { a: 1 };
obj.a = 2; // allowed — object properties are still mutable

// obj = { a: 3 }; // Error: Assignment to constant variable.

const arr = [1,2];
arr.push(3); // allowed

// arr = [4]; // Error
```

Ways to enforce immutability:

- Use `readonly` in TypeScript for fields / tuple/array types:

```ts
type ReadonlyPoint = { readonly x: number; readonly y: number };
const p: ReadonlyPoint = { x: 1, y: 2 };
// p.x = 3; // Error in TS
```

- Use `as const` assertion to make array/objects deeply readonly at the type level and narrow literal types:

```ts
const tuple = [1, 2] as const; // type is readonly [1, 2]
```

- Use `Object.freeze()` for shallow runtime immutability (prevents property reassignment at runtime but is shallow):

```ts
const frozen = Object.freeze({ a: 1 });
// frozen.a = 2; // silently fails in non-strict mode or throws in strict mode
```

Summary: `const` prevents reassignment of the binding, not deep immutability. Use `readonly`, `as const` and runtime freezes when you need immutability.

---

## 5. Arrays, tuples and objects

```ts
const nums: number[] = [1,2,3];
const tuple: [string, number] = ["id", 5];
const obj: { id: number; name: string } = { id: 1, name: 'Gabi' };
```

Tuples have fixed size and types.

---

## 6. Enums

TypeScript `enum` generates a runtime object (numeric or string). In C++ enums are compile-time constructs and more efficient.

```ts
enum Direction { Up, Right, Down, Left }
const d = Direction.Up; // 0

enum Color { Red = "red", Blue = "blue" }
```

If you want a zero-cost alternative (no runtime object), use string unions:

```ts
type Dir = 'Up' | 'Right' | 'Down' | 'Left';
```

---

## 7. Functions (signatures, optional params, rest, overload)

```ts
function add(a: number, b: number): number { return a + b; }
function greet(name?: string) { console.log(name ?? 'friend'); }
function product(...vals: number[]): number { return vals.reduce((s, v) => s * v, 1); }
```

Overloads in TS are multiple type signatures with a single implementation.

---

## 8. Classes, inheritance and modifiers

Syntax looks similar to C++ but compiles to JS prototype-based classes.

Modifiers: `public`, `private`, `protected`, `readonly`, `static`.

```ts
class Person {
  constructor(public name: string, private age: number) {}
  public speak() { return `Hi, ${this.name}`; }
}
```

Note: `private`/`protected` are compiler-checked; properties still exist on the object at runtime unless you use ES `#private` fields.

---

## 9. Interfaces vs type aliases

`interface` defines an object contract (structural). `type` creates aliases and unions. Prefer `interface` for public contracts and `type` for composites.

```ts
interface Player { id: string; hp: number; inventory: string[] }
type ID = number | string;
```

TypeScript uses structural typing (compatibility by shape), unlike C++ nominal typing.

---

## 10. Generics vs Templates

- C++ templates generate code per instance at compile time (monomorphization).
- TS generics exist only at the type level and do not produce separate runtime instances for each type parameter.

```ts
function identity<T>(x: T): T { return x; }
```

Implication: there is no separate runtime specialization per `T` — only static checking.

---

## 11. Modules and imports

Use `export` / `import` (ES modules) or CommonJS (`module.exports` / `require`) depending on your `tsconfig`.

```ts
// math.ts
export function add(a: number, b: number) { return a + b }

// app.ts
import { add } from './math';
```

---

## 12. Concurrency: Promises / async vs threads

- JS/TS is single-threaded by default (event loop). For parallelism, use Workers, child_process or cluster in Node.
- `async`/`await` and `Promise` model asynchronous (non-blocking) operations, different from threads and locks in C++.

```ts
async function fetchData() { return await fetch('/'); }
```

Think in events and asynchronous flows rather than fine-grained thread synchronization.

---

## 13. Memory and runtime

- JS has a Garbage Collector (GC). There are no deterministic destructors (RAII does not exist).
- Use `try/finally` for cleanup and `dispose()` patterns when needed.

---

## 14. Best practices and common pitfalls for ex-C++ devs

- Avoid `any` — it defeats the purpose of TypeScript.
- Use `===` instead of `==` (strict equality).
- Enable `strictNullChecks` to catch `null`/`undefined` issues.
- Numeric operations follow IEEE-754 floating point rules.
- Compiler type checks do not guarantee runtime safety for untrusted data; validate external JSON and inputs.

---

## 15. Full example (file `src/ts_for_cpp_example.ts`)

```ts
// Example: Player and GameState simple model

enum Phase { Planning, Movement, Action, Fishing, Market }

interface Player { id: string; hp: number; coins: number; sea: string; inventory: string[] }

class GameState {
  constructor(public turn: number = 1, public phase: Phase = Phase.Planning, public players: Player[] = []) {}

  nextPhase() { this.phase = (this.phase + 1) % 5; }

  addPlayer(p: Player) { this.players.push(p); }
}

const gs = new GameState();
gs.addPlayer({ id: 'p1', hp: 10, coins: 0, sea: 'SEA_1', inventory: [] });
console.log(gs);
```

Note: iterating over enums with `Object.keys()` requires care because numeric enums create both numeric and string keys.

---

## 16. Tools and workflow

- `tsc` compiles to JavaScript (`.js`).
- `ts-node` runs TypeScript directly (good for prototyping).
- `npm`/`pnpm`/`yarn` for dependency management.
- Configure `tsconfig.json` with `strict: true` for stronger checks.

Useful commands:

```bash
npm install -D typescript ts-node @types/node
npx tsc --init
npx ts-node src/ts_for_cpp_example.ts
```

---

## 17. Quick checklist for shifting mindset C++ → TS

- Stop thinking in pointers/addresses and start thinking in references and GC-managed objects.
- Prefer pure functions and immutability where possible (`const`, `readonly`).
- Model public contracts with `interface` and `type`.
- Write small tests to validate asynchronous behavior.

---

If you want, I can create `src/ts_for_cpp_example.ts`, a minimal `package.json` and `tsconfig.json` in this repository and run the example. Reply "Generate scaffold" to add those files or "Document only" if you prefer only the translated document.
