# JavaScript Complete Learning Roadmap

### Beginner → Advanced → Professional Engineer

---

# 🟢 PHASE 1 — Language Foundations

---

## Chapter 1: Introduction to JavaScript

- What is JavaScript & Why It Powers the Web
- JavaScript vs Java vs Other Languages
- ECMAScript Standard — ES Versions (ES3 → ES2024+)
- JS Engines — V8, SpiderMonkey, JavaScriptCore
- How JS Runs in the Browser
- Browser JS vs Node.js JS
- Linking JS with HTML using the `<script>` tag
- Script Loading — `defer` and `async` attributes
- Running JavaScript in the Browser Console
- Using Console for Debugging & Testing
    - `console.log()`, `console.info()`, `console.warn()`, `console.error()`, `console.table()`, `console.trace()`
- Interactions — `alert()`, `prompt()`, `confirm()`

---

## Chapter 2: Syntax & Language Rules

- Statements vs Expressions — what they are and the difference
- Semicolons & ASI (Automatic Semicolon Insertion) — rules and edge cases
- Identifiers — Naming rules, Case Sensitivity, Reserved Words
- Keywords & Reserved Words (complete list awareness)
- Comments — Single-line `//`, Multi-line `/* */`, JSDoc intro `/** */`
- Strict Mode — `"use strict"` and why it matters

---

## Chapter 3: Variables & Scope

- `var` vs `let` vs `const` — full comparison
- The Variable Lifecycle — Declaration → Initialization → Assignment
- Re-Declaration & Re-Assignment rules per keyword
- Hoisting — Variable Hoisting vs Function Hoisting
- Temporal Dead Zone (TDZ)
- Scope Types
    - Global Scope
    - Function Scope
    - Block Scope
- Global Scope Pollution and how to avoid it
- **Q: Why does `var` leak out of a block `{}` but `let` doesn't?**
- **Q: Why does `const` allow mutation of object properties?**
- Best Practices for Variables

---

## Chapter 4: Data Types

### Primitive Types

- `string`, `number`, `boolean`, `null`, `undefined`, `symbol`, `bigint`

### Non-Primitive (Reference) Types

- `object`, `array`, `function`, `date`, `regexp`, `Map`, `Set`

### Special Values

- `NaN`, `undefined`, `null`, `Infinity`, `-0`
- `typeof null === 'object'` — the infamous quirk
- `typeof NaN === 'number'` — explained

### Core Concepts

- Primitive vs Reference Types
- Memory — Stack (Primitives) vs Heap (Reference Types)
- Pass by Value vs Pass by Reference
- Type Coercion — Implicit vs Explicit
- Type Casting — `Number()`, `String()`, `Boolean()`
- Truthy vs Falsy values — complete list
- `isEmpty()` logic and checking for existence
- `==` vs `===` — abstract vs strict equality
- **Q: Why does `"5" + 1 === '51'` but `"5" - 1 === 4`?**

---

## Chapter 5: Operators

### Arithmetic Operators

- `+`, `-`, `*`, `/`, `%`, `**`
- Unary `+`, unary `-`
- Increment/Decrement — `++` (pre/post), `--` (pre/post)

### Comparison Operators

- `==`, `!=`, `===`, `!==`, `<`, `>`, `<=`, `>=`
- Object Comparison — why `{} !== {}`

### Logical Operators

- `&&` (AND), `||` (OR), `!` (NOT)
- Short-Circuit Evaluation
- `!!` operator for coercing to boolean
- Nullish Coalescing `??`

### Assignment Operators

- `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `**=`
- Logical Assignment — `&&=`, `||=`, `??=`

### Special Operators

- `typeof` — runtime type checking
- `instanceof` — prototype chain check
- `in` — property existence in object
- `delete` — remove object property
- Optional Chaining `?.`
- Spread `...` and Rest `...`
- Ternary Operator `? :`
- Nested Conditions with Ternary

### Bitwise Operators

- `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>`

---

## Chapter 6: Numbers & Math

### Numbers

- Integer vs Floating Point
- IEEE 754 Issues — floating point precision problems
- `NaN` and `Infinity` in depth

### Number Methods

- `Number()`, `parseInt()`, `parseFloat()`
- `isNaN()`, `isFinite()`
- `toFixed()`, `toPrecision()`, `toString(radix)`

### BigInt

- BigInt for large integers — syntax and limitations

### Math Object (Complete)

- `Math.abs`, `Math.round`, `Math.floor`, `Math.ceil`, `Math.trunc`
- `Math.random`, `Math.min`, `Math.max`
- `Math.pow`, `Math.sqrt`, `Math.cbrt`
- `Math.sign`, `Math.clz32`, `Math.imul`
- Trigonometric — `Math.sin`, `Math.cos`, `Math.tan`

---

# 🟡 PHASE 2 — Logic, Data Structures & Strings

---

## Chapter 7: Control Flow — Conditionals

- `if`, `else`, `else if` branching
- Nested Conditions
- Ternary Operator `? :`
- `switch` Statement — Fall-Through Behavior, `break`
- **Q: When to use switch vs if-else?**

---

## Chapter 8: Control Flow — Loops

- `for` loop — standard iteration
- `while` loop
- `do...while` loop
- `for...in` — iterating object keys
- `for...of` — iterating iterables
- `forEach` — array iteration callback
- Recursion — concept, base case, stack behavior
- Loop Control — `break`, `continue`
- Labeled Loops
- **Q: `for...in` vs `for...of` — key differences**

---

## Chapter 9: Strings (Complete)

### Creation

- String Literals, `String()` constructor, Template Literals (tagged templates)

### Properties

- `length`

### Character Access

- `charAt()`, `charCodeAt()`, `at()`, Bracket Notation `[]`

### Searching & Checking

- `includes()`, `startsWith()`, `endsWith()`
- `indexOf()`, `lastIndexOf()`
- `search()`, `match()`, `matchAll()`

### Manipulation

- `slice()`, `substring()`, `substr()` (deprecated, but seen in legacy)
- `replace()`, `replaceAll()`
- `concat()`, `repeat()`, `padStart()`, `padEnd()`

### Formatting

- `toUpperCase()`, `toLowerCase()`
- `trim()`, `trimStart()`, `trimEnd()`
- `normalize()`

### Conversion

- `split()`, `toString()`, `valueOf()`

---

## Chapter 10: Regular Expressions

- What are Regular Expressions and why they matter
- Creating RegExp — Literal `/pattern/` and `new RegExp()` constructor
- Flags — `g`, `i`, `m`, `s`, `u`, `y`, `d`, `v` (ES2024 — set notation & Unicode)

### Core Methods on String

- `match()`, `matchAll()`, `search()`, `replace()`, `replaceAll()`, `split()`

### RegExp Methods

- `test()`, `exec()`

### Patterns

- Anchors — `^`, `$`
- Quantifiers — `*`, `+`, `?`, `{n}`, `{n,m}`
- Character Classes — `\d`, `\w`, `\s`, `.`
- Groups & Capturing — named `(?<name>...)`, non-capturing `(?:...)`
- Lookahead — `(?=...)`, `(?!...)`
- Lookbehind — `(?<=...)`, `(?<!...)`

### Real-World Patterns

- Email validation, URL parsing, password strength
- Phone numbers (international), date formats, currency extraction

### Performance

- Backtracking pitfalls, catastrophic backtracking

---

## Chapter 11: Arrays (Complete)

### Creation

- `[]`, `Array()`, `Array.of()`, `Array.from()`

### Mutating Methods

- `push`, `pop`, `shift`, `unshift`
- `splice`, `sort`, `reverse`, `fill`, `copyWithin`

### Non-Mutating Methods (ES2023+)

- `slice`, `concat`
- `toSorted()`, `toReversed()`, `toSpliced()`, `with()`

### Iteration & Transformation

- `forEach`, `map`, `filter`, `reduce`, `reduceRight`
- `some`, `every`, `find`, `findIndex`
- `findLast`, `findLastIndex`

### Searching

- `includes`, `indexOf`, `lastIndexOf`, `at()`

### Other Methods

- `join`, `flat`, `flatMap`

### Destructuring & Spread

- Array Destructuring
- Spread Operator `...`

### **Q&A**

- `splice` vs `slice`
- `map` vs `forEach`
- `sort` behavior without `compareFn` (gotcha!)

---

## Chapter 12: Sets & Maps

### Set

- Set as a collection of unique values
- `add`, `delete`, `has`, `clear`, `size`
- Iterating Sets — `forEach`, `for...of`
- Removing duplicates elegantly

### New Set Methods (ES2024+)

- `union(other)`, `intersection(other)`, `difference(other)`, `symmetricDifference(other)`
- `isSubsetOf(other)`, `isSupersetOf(other)`, `isDisjointFrom(other)`

### Map

- Map vs Object — when to use which
- `set`, `get`, `has`, `delete`, `clear`, `size`
- Iterating Maps — `keys()`, `values()`, `entries()`

### WeakSet & WeakMap

- Weak references, garbage collection implications
- Use cases in caching and private data

---

## Chapter 13: Objects (Complete)

### Basics

- Object Literals — `{}` syntax
- Key-Value Pairs — properties and values
- Dot Notation vs Bracket Notation `[]`
- Computed Properties — `{ [varName]: value }`
- Shorthand Syntax
- Nested Objects & Deep Access

### Creating & Modifying

- Adding, Updating, Deleting Properties (`delete`)
- Optional Chaining `?.`

### Destructuring

- Object Destructuring
- Renaming during destructuring — `{ "first-name": firstName }`
- Default values in destructuring

### Looping

- `for...in`, `Object.keys()`, `Object.values()`, `Object.entries()`

### Object Methods (Complete)

- `Object.keys()`, `Object.values()`, `Object.entries()`
- `Object.assign()`, `Object.fromEntries()`
- `Object.freeze()`, `Object.seal()`, `Object.preventExtensions()`
- `Object.hasOwn()`, `Object.is()`
- `Object.getPrototypeOf()`, `Object.setPrototypeOf()`

### Copying Objects

- Shallow Copy — Spread `...`, `Object.assign()`
- Deep Clone — `JSON.stringify` + `JSON.parse` (+ limitations)
- `structuredClone()` — modern deep clone

### `this` Keyword in Objects

- Global `this`, Method `this`, Arrow Function `this`
- `call`, `apply`, `bind`

### Memory

- How Objects are Stored in Memory
- Reference Copy vs Deep Clone

### **Q: Why does `{}` passed into a function mutate the original?**

---

# 🟠 PHASE 3 — Functions & The Functional Core

---

## Chapter 14: Functions (Deep)

### Declaration Styles

- Function Declaration
- Function Expression
- Arrow Functions (`=>`) — differences from regular functions
- Anonymous Functions
- Named Function Expressions

### Parameters & Arguments

- Required, Default, Destructured, Rest Parameters `...rest`
- Positional, Default, Spread Arguments

### Return Behavior

- Implicit vs Explicit `return`
- Functions returning functions

### Function Types

- First-Class Functions — functions as values
- Higher-Order Functions (HOF)
- Callback Functions
- Pure Functions — same input, same output, no side effects
- Impure Functions — side effects

### Hoisting

- Function Declaration hoisting vs Function Expression (TDZ)

### Scope & Scope Chain

- Global Scope, Function Scope, Block Scope
- Lexical Scoping — determined by where code is written
- Scope Chain traversal

### `this` in Depth

- Global `this`
- Method `this`
- Arrow functions don't have their own `this` — they inherit from parent
- `call`, `apply`, `bind` — explicit binding

### IIFE — Immediately Invoked Function Expression

- Syntax and purpose
- Isolating variables with IIFE

### Closures

- Definition — inner function accessing outer function's scope after outer has returned
- Lexical Environment `[[Environment]]`
- Private Variables using Closures
- Preventing Global Pollution
- Use Cases — private counters, encapsulation, memoization
- Memory implications of closures

### Currying & Partial Application

- Currying — `f(a)(b)(c)` from `f(a, b, c)`
- Partial Application — fixing some arguments
- Use in middleware, utilities, functional programming

### **Practice Problems**

- Build a counter using Closures
- Create a reusable discount calculator
- Use IIFE to isolate variables

---

## Chapter 15: Execution Context & Call Stack

- What is an Execution Context — the "box" JS creates to run code
- Global Execution Context
- Function Execution Context
- Two Phases
    - Memory Phase — allocates space for variables and functions
    - Execution Phase — actual code runs
- The Call Stack — how contexts stack up
- Stack Overflow — recursive pitfall
- The Heap & Garbage Collection (Mark-and-Sweep algorithm)

---

## Chapter 16: Advanced Scope & Closures (Deep Dive)

- Lexical Scope vs Dynamic Scope (JS uses Lexical)
- Closure Mechanics — the `[[Scope]]` / `[[Environment]]` link
- Variable Preservation via backlink
- Closure Traps — stale closures in loops (`var` vs `let`)
- Memory Leaks from Closures — what to watch for
- **Q: Build a memoization function using closures**

---

## Chapter 17: Functional Programming Concepts

- Immutability — treating data as unchangeable
- Pure Functions & Referential Transparency
- Function Composition — `compose(f, g)(x)`
- Currying & Partial Application (applied depth)
- Avoiding Shared State and Side Effects
- Map, Filter, Reduce as FP primitives
- Thinking functionally vs imperatively

---

# 🔵 PHASE 4 — OOP & Prototypes

---

## Chapter 18: Prototypes & Inheritance Model

- `prototype` property on functions
- `__proto__` — the prototype chain link
- `Object.getPrototypeOf()` and `Object.setPrototypeOf()`
- Prototype Chain traversal
- `hasOwnProperty` vs inherited properties
- Constructor Functions — pre-ES6 OOP pattern
- Prototype-Based Inheritance

---

## Chapter 19: OOP with Classes (ES6+)

### Core OOP Concepts

- Encapsulation, Abstraction, Inheritance, Polymorphism

### Class Syntax

- `class` keyword, `constructor()`
- Instance Methods & Properties
- Static Methods & Static Properties
- Getters `get` and Setters `set`
- Private Fields `#` (ES2022)
- Class Expressions
- Class Hoisting (classes are NOT hoisted like functions)

### Inheritance

- `extends` — subclassing
- `super` — calling parent constructor and methods
- Method Overriding

### OOP Patterns

- Factory Functions — creating objects without `new`
- Module Pattern (IIFE-based)
- Revealing Module Pattern
- Mixins — composing behaviors

---

## Chapter 20: SOLID Principles in JavaScript

- Single Responsibility Principle
- Open/Closed Principle
- Liskov Substitution Principle
- Interface Segregation Principle
- Dependency Inversion Principle
- Composition over Inheritance — when and why

---

## Chapter 21: Design Patterns in JavaScript

- What Design Patterns are and why they matter
- Module Pattern
- Revealing Module Pattern
- Factory Function Pattern
- Observer Pattern (event-driven systems)
- Singleton Pattern
- When and why to use each pattern

---

# 🟣 PHASE 5 — Asynchronous JavaScript

---

## Chapter 22: Asynchronous JavaScript — Foundations

- Synchronous vs Asynchronous execution
- The JavaScript Runtime — single-threaded explained
- Call Stack, Web APIs, Task Queue, Microtask Queue
- Callbacks — how they work
- Callback Hell (Pyramid of Doom) — the problem

---

## Chapter 23: The Event Loop (Deep Dive)

- Event Loop phases — Timers → Pending Callbacks → Idle/Prepare → Poll → Check → Close Callbacks
- Macrotasks vs Microtasks
    - Macrotasks — `setTimeout`, `setInterval`, browser events
    - Microtasks — `Promise.then`, `queueMicrotask`, `MutationObserver`
- Priority Order — Microtasks drain before next Macrotask
- Microtask Starvation of the Macrotask queue
- Rendering Cycle — where paint fits in the loop
- Visualizing with tools like Loupe or browser DevTools

---

## Chapter 24: Timers & Scheduling

- `setTimeout()` and `clearTimeout()`
- `setInterval()` and `clearInterval()`
- Recursive `setTimeout` vs `setInterval` — drift issues
- `requestAnimationFrame` — frame lifecycle, canceling, performance comparison
- Timers in relation to the Event Loop

---

## Chapter 25: Promises

- Promise States — Pending, Fulfilled, Rejected
- Creating Promises — `new Promise((resolve, reject) => {})`
- `.then()`, `.catch()`, `.finally()`
- Promise Chaining
- Error propagation through chains

### Promise Combinators

- `Promise.all()` — all or fail
- `Promise.allSettled()` — all with results
- `Promise.race()` — first settled
- `Promise.any()` — first fulfilled
- `Promise.withResolvers()` (ES2024)

---

## Chapter 26: async / await

- `async` function — always returns a Promise
- `await` — pausing inside async function
- Error Handling with `try / catch / finally`
- Sequential vs Parallel Execution
    - Sequential — `await a; await b;`
    - Parallel — `await Promise.all([a, b])`
- Async Patterns — retry logic, backoff algorithms
- Cancellation Patterns with `AbortController`
- Race Conditions and how to avoid them

---

## Chapter 27: Advanced Async Patterns

- Sequential Async Flows
- Parallel Async Flows
- Retry Strategies with exponential backoff
- Cancellation with `AbortController`
- Async Iterators — `for await...of`
- Starvation and queue management

---

# 🟤 PHASE 6 — DOM & Browser APIs

---

## Chapter 28: The DOM — Fundamentals

- What is the DOM — Document Object Model
- DOM Tree Structure — Nodes, Elements, Text, Comment, Document
- Nodes vs Elements distinction
- Live vs Static NodeLists — `getElementsBy*` vs `querySelectorAll`
- DOM vs Virtual DOM (conceptual overview)

---

## Chapter 29: DOM Selection

### Basic Selectors

- `getElementById`, `getElementsByClassName`, `getElementsByTagName`

### Modern Selectors

- `querySelector`, `querySelectorAll`
- CSS Selector syntax support
- `closest()` — find nearest ancestor matching selector
- `contains()` — check containment

### Performance Differences

- When to use which selector

---

## Chapter 30: DOM Traversal

- `parentNode`, `parentElement`
- `children`, `childNodes`
- `firstChild`, `lastChild`, `firstElementChild`, `lastElementChild`
- `nextSibling`, `previousSibling`
- `nextElementSibling`, `previousElementSibling`

---

## Chapter 31: DOM Manipulation

### Create & Insert

- `createElement`, `createTextNode`
- `append`, `appendChild`, `prepend`, `insertBefore`
- `insertAdjacentElement`, `insertAdjacentHTML`, `insertAdjacentText`
- `DocumentFragment` — batch insertions for performance

### Remove & Replace

- `remove()`, `removeChild()`
- `replaceChild()`, `replaceWith()`

### Content Access

- `innerHTML`, `outerHTML` — with XSS security warning
- `innerText`, `textContent` — differences explained
- Performance considerations

---

## Chapter 32: DOM Attributes, Properties & Styling

### Attributes

- `getAttribute`, `setAttribute`, `removeAttribute`, `hasAttribute`
- Attribute vs Property difference
- `dataset` — `data-*` attributes
- Boolean Attributes
- ARIA Attributes — `aria-label`, `aria-hidden`, `role`

### Styling

- `style` property — inline styles
- `getComputedStyle` — reading applied styles
- CSS Variables `--var` via JS
- `className` — full class string
- `classList` — `add`, `remove`, `toggle`, `contains`, `replace`

---

## Chapter 33: Forms & Input Handling (Deep)

- Form Elements — `input`, `textarea`, `select`, `checkbox`, `radio`
- Reading values — `value`, `checked`, `selectedIndex`
- Form Submission Lifecycle
- `FormData` API
- `preventDefault()` — stop default submit
- Client-Side Validation
- Constraint Validation API
- Custom Validation Messages
- Showing error messages conditionally
- Pattern attribute vs Custom Regex validation
- **Differences: `value` vs `textContent`, form submission vs button click**

---

## Chapter 34: Events System

### Core

- Event Object — `type`, `target`, `currentTarget`, `preventDefault`, `stopPropagation`
- Event Phases — Capturing → Target → Bubbling
- Cancelable Events

### Binding & Options

- `addEventListener` — options (`once`, `passive`, `capture`)
- `removeEventListener` — named handler requirement
- `AbortController` for removing event listeners

### Event Types (Complete)

**Mouse Events** — `click`, `dblclick`, `mousedown`, `mouseup`, `mousemove`, `mouseenter`, `mouseleave`, `mouseover`, `mouseout`, `contextmenu`

**Keyboard Events** — `keydown`, `keyup`, `keypress` (deprecated), Key Codes vs Key Values

**Form Events** — `submit`, `change`, `input`, `focus`, `blur`, `reset`

**Window/Document Events** — `load`, `DOMContentLoaded`, `resize`, `scroll`, `visibilitychange`

### Event Delegation

- Bubbling-based delegation pattern
- Handling dynamically created elements
- Performance benefits
- `event.target` vs `event.currentTarget`
- Common pitfalls

---

## Chapter 35: Browser Object Model (BOM)

### Window Object

- `window` as the global object
- `window.open`, `window.close`
- `devicePixelRatio`

### Location Object

- `location.href`, `location.protocol`, `location.host`, `location.pathname`
- `location.search`, `location.hash`
- `location.assign()`, `location.replace()`, `location.reload()`

### History API

- `history.back()`, `history.forward()`, `history.go()`
- `pushState()`, `replaceState()`
- SPA Navigation Concepts

### Navigator Object

- `navigator.userAgent`, `navigator.platform`, `navigator.language`
- `navigator.onLine`
- Feature Detection patterns

---

## Chapter 36: Storage & Cookies

- `localStorage` — `setItem`, `getItem`, `removeItem`, `clear`
- `sessionStorage` — same API, different lifespan
- Differences between `localStorage` and `sessionStorage`
- Why only strings work — JSON serialization with `JSON.stringify` / `JSON.parse`
- Cookies — basic `key=value; path=/` structure
- Cookie expiration and `HttpOnly`, `Secure` flags
- Storage Events — listening to changes across tabs
- Quota limits
- `IndexedDB` — intro for large structured data
- `Cache API` — intro

---

## Chapter 37: Fetch API & HTTP

### HTTP Basics

- HTTP Methods — `GET`, `POST`, `PUT`, `PATCH`, `DELETE`
- Headers, Status Codes
- CORS — Same-Origin Policy

### Fetch API

- `fetch()` — Request/Response objects
- Handling response types — JSON, text, blob, FormData
- Error handling — Network errors vs HTTP errors (status checks)
- `AbortController` — canceling requests, timeout handling
- Retry Logic — wrapping fetch with retry
- File Uploads & Download Blobs
- Custom fetch helpers / interceptors
- Authentication flows — tokens in headers, refresh tokens (conceptual)

### JSON Handling

- `JSON.stringify()` — serializing
- `JSON.parse()` — deserializing
- Replacers, revivers, spacing

---

## Chapter 38: Observer APIs

- `IntersectionObserver` — lazy loading, infinite scroll, animations on scroll
- `MutationObserver` — watching DOM changes
- `ResizeObserver` — watching element size changes
- Performance use cases and patterns

---

# 🔴 PHASE 7 — Error Handling, Modules & Tooling

---

## Chapter 39: Error Handling

### Types of Errors

- Syntax Errors, Runtime Errors, Logical Errors

### Error Object

- `message`, `name`, `stack`

### Handling

- `try`, `catch`, `finally`
- Throwing Errors — `throw new Error()`
- Custom Error Classes — extending `Error`

### Async Error Handling

- Errors in Promises — `.catch()`
- Errors in `async/await` — `try/catch`
- Unhandled rejection events

---

## Chapter 40: ES Modules

- Why Modules — scalable code organization
- Named Exports & Named Imports
- Default Exports & Imports
- `import * as` namespace imports
- Dynamic Imports — `import()` — code splitting
- CommonJS (`require`) vs ES Modules (`import`) — key differences
- Module Resolution
- Using modules with bundlers — Webpack, Vite (overview)
- `require()` in Node.js vs `import` in ESM

---

## Chapter 41: Dates & Time

### Legacy Date Object

- `new Date()` constructors — various forms
- `Date.now()`, `Date.parse()`
- Date Getters — `getFullYear()`, `getMonth()` (0-based!), `getDate()`, `getHours()`
- Date Setters — `setHours()`, `setDate()`, etc.
- Common pitfalls — 0-based months, mutability, DST issues

### Intl API (Modern — Very Important)

- `Intl.DateTimeFormat` — locale-specific formatting, `dateStyle`, `timeStyle`, weekday, era, year, month, day
- `Intl.RelativeTimeFormat` — "2 hours ago", "in 3 days"
- `Intl.NumberFormat` — currency, percentages, compact notation
- `Intl.PluralRules` — "1 item" vs "5 items"
- `Intl.ListFormat` — "apples, bananas, and oranges"
- `Intl.Collator` — locale-aware string comparison/sorting

### Real-World Examples

- Formatting dates for different countries (en-US, hi-IN, fr-FR)
- Countdown timers, age calculation
- Event scheduling across timezones

### Popular Libraries (Brief Mention)

- `date-fns` — modern & tree-shakeable
- `Luxon` — powerful & timezone-friendly

### Temporal Proposal (2026 Status)

- Brief overview of `Temporal` API
- Why it replaces `Date` in future
- Current polyfill availability

---

## Chapter 42: Generators & Iterators

### Iterators

- The Iterator Protocol — `Symbol.iterator`
- Custom Iterators — implementing `next()` returning `{ value, done }`
- Iterables vs Iterators

### Generators

- `function*` syntax
- `yield` — pausing execution
- `yield*` — delegating to another iterable
- `next()`, `return()`, `throw()` on generator objects

### Use Cases

- Lazy evaluation — generating values on demand
- Infinite sequences
- Data streaming
- Coroutines
- Async Iterators — `async function*`, `for await...of`

---

# ⚫ PHASE 8 — Performance, Security & Professional Practices

---

## Chapter 43: Performance Optimization

### JavaScript Performance

- Debouncing — delaying execution until user stops (search input)
- Throttling — limiting execution rate (scroll handlers)
- Memoization — caching function results
- Avoiding Memory Leaks — detached DOM, forgotten listeners, closures

### DOM Performance

- Reflows & Repaints — what triggers them
- Layout Thrashing — reading then writing DOM in loops
- DOM Batching — `DocumentFragment`, batch reads/writes
- `requestAnimationFrame` for smooth animations
- Virtualization — only rendering visible list items
- Lazy Rendering

### Load Performance

- Lazy Loading — images, components
- Code Splitting — dynamic `import()`
- `defer` and `async` for scripts

### Profiling Tools

- Chrome DevTools — Performance tab
- Lighthouse audits
- `performance.now()` for precise timing

---

## Chapter 44: Security Fundamentals

### Client-Side Security

- XSS (Cross-Site Scripting) — injection via `innerHTML`, prevention with escaping
- DOM-based XSS
- Sanitization Libraries — DOMPurify
- `eval()` — why to never use it
- Content Security Policy (CSP)
- Same-Origin Policy

### Network Security

- CSRF (Cross-Site Request Forgery) — overview and tokens
- Secure Cookie handling — `HttpOnly`, `Secure`, `SameSite`
- HTTPS and why it matters
- Secure fetch requests

### Best Practices

- Strict Mode enforcement
- Avoiding global pollution
- Input validation and sanitization

---

## Chapter 45: Testing & Debugging

### Debugging

- Chrome DevTools — breakpoints, watch expressions, call stack
- `debugger` statement
- Source Maps — debugging minified code
- Network tab for API debugging

### Unit Testing

- Why testing matters — job-ready code
- Jest or Mocha — setup, `describe()`, `it()`, `expect()`
- Common assertions — `toBe`, `toEqual`, `toContain`, `toThrow`
- Testing Async Code — `async/await` in tests, mocking Promises
- Mocking functions and modules

### Code Coverage

- Coverage basics — lines, branches, functions
- Integration with CI/CD (overview)

---

## Chapter 46: TypeScript Essentials for JS Developers

- Why TypeScript — type safety, tooling, scalability
- Basic Types — `string`, `number`, `boolean`, `any`, `unknown`, `void`, `never`
- Interfaces vs Type Aliases — when to use which
- Union Types `|` and Intersection Types `&`
- Type Guards — `typeof`, `instanceof`, custom guards
- Generics — reusable type-safe functions and interfaces
- Enums
- `tsconfig.json` — key compiler options
- TypeScript Compiler `tsc`
- Linting and Formatting with TypeScript
- Typing Fetch responses (overview)
- Common Integrations — TypeScript with React, Node.js

---

# 🔶 PHASE 9 — Advanced Browser APIs & Node.js Context

---

## Chapter 47: Advanced Web APIs

### Service Workers & PWA Basics

- Registration lifecycle — install, activate, fetch
- Caching strategies — cache-first, network-first
- Offline capabilities

### Web Workers

- Dedicated Workers — `Worker` API
- Shared Workers
- `postMessage()` — communicating with workers
- Offloading heavy computation to background threads
- Concurrency handling

### Canvas API

- `getContext('2d')`
- Drawing shapes, paths, text
- Working with images
- Basic animations on Canvas

### Other Web APIs

- Geolocation — `navigator.geolocation`, permissions, accuracy, error handling
- Notifications — `Notification` API, permissions
- Clipboard — `navigator.clipboard.read()` / `write()`
- File & Blob — `FileReader`, `Blob`, `URL.createObjectURL()`
- File Input Handling — reading user-uploaded files

### Performance APIs

- `Performance` object
- `performance.now()` — precise timing
- `PerformanceObserver`

---

## Chapter 48: Accessibility (a11y) in JavaScript

- Why accessibility matters — legal, ethical, broader audience
- Semantic HTML + JS — using the right elements
- ARIA Roles and Attributes — `aria-label`, `aria-hidden`, `aria-live`, `role`
- Keyboard Navigation — `tabindex`, `focus()`, `blur()`
- Focus Management in SPAs — restoring focus after navigation
- Screen Reader Considerations — Live Regions, announcing dynamic content
- Form Accessibility — labels, error messages, validation feedback
- Tools — Lighthouse, WAVE, axe DevTools

---

## Chapter 49: Node.js-Specific JavaScript (Backend Context)

- `process.env` — environment variables
- Buffer and Streams basics — file uploads, large responses
- `fs.promises` — async file system operations
- `util.promisify` — converting callbacks to Promises
- Event Emitters — `EventEmitter`, custom events
- CommonJS modules in Node vs ESM
- `require()` vs `import`
- Cluster module — scaling Node with multiple processes
- `worker_threads` — parallelism in Node.js
- npm — package management, `package.json`, scripts

---

## Chapter 50: Tooling & Professional Workflow

### Package Management

- npm — installing, updating, scripts
- `package.json` and `package-lock.json`
- Semantic versioning

### Bundlers (Overview)

- Webpack — concepts, loaders, plugins
- Vite — modern, fast dev server
- Why bundlers exist — module resolution, tree shaking, minification

### Linters & Formatters

- ESLint — catching errors and enforcing style
- Prettier — automatic code formatting
- `.eslintrc` and `.prettierrc` configuration

### Version Control Basics

- Git fundamentals for JS developers

---

# 🟥 APPENDIX — Ultra-Advanced & Specialized Topics

_These topics are not prerequisites for most roles but represent deep expertise. Study after completing Phases 1–8._

---

## A1: Memory Management Internals

- V8 Garbage Collection — Scavenger (Young Gen) & Mark-Compact (Old Gen)
- Memory Leak patterns — detached nodes, event listeners, closures
- Heap snapshots in Chrome DevTools
- `WeakRef` and `FinalizationRegistry`

## A2: JavaScript Engine Internals

- V8 — Ignition interpreter, TurboFan JIT compiler
- Inline Caching
- Hidden Classes — why shape consistency matters for performance
- Deoptimization triggers

## A3: Metaprogramming

- `Proxy` — intercepting object operations
- `Reflect` — mirroring object operations
- `Symbol` — well-known Symbols (`Symbol.iterator`, `Symbol.toPrimitive`, `Symbol.hasInstance`)
- Property Descriptors — `Object.defineProperty`, `writable`, `enumerable`, `configurable`

## A4: Advanced Patterns

- Event Sourcing pattern
- Command pattern
- Strategy pattern
- Middleware pattern (Express-style)

## A5: WebAssembly & JS Interop (Overview)

- What WebAssembly is and where JS calls into it
- Use cases — performance-critical code, porting C/C++/Rust

## A6: Web Streams API

- `ReadableStream`, `WritableStream`, `TransformStream`
- Piping streams
- Fetch + Streams for large downloads

## A7: Internationalization Deep Dive

- All `Intl` constructors in full depth
- Locale negotiation
- Sorting, collation, number systems

## A8: Progressive Web Apps (PWA) — Deep

- App Manifest
- Service Worker lifecycle in full detail
- Push Notifications
- Background Sync
- IndexedDB for offline data

---

_End of Roadmap_

---

> **How to use this roadmap:** Work through Phases 1–5 sequentially — they are strictly ordered. Phases 6–7 can be explored in parallel after Phase 5. Phase 8–9 is professional-grade work. The Appendix is for when you want to go deeper than most developers ever do.