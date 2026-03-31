Bhai, agar variables **data** hain, toh operators **actions** hain — woh kaam karne wale tools hain jo data pe operations perform karte hain. Is chapter ke baad tum code mein har jagah operators confidently use kar paoge!

---

## 1. 🧠 Simple Explanation (ELI5)

Socho tumhare paas ingredients hain (variables/values) aur tumhe khaana banana hai. **Operators** woh **cooking tools** hain:

> `+` = mixing bowl (cheezein add karo) `-` = chhilna (kuch hatao) `>` = weighing scale (compare karo) `&&` = AND gate ("yeh **aur** woh dono chahiye") `||` = OR gate ("yeh **ya** woh — koi ek chalega") `??` = backup plan ("pehla nahi mila toh doosra lo") `?.` = safety check ("pehle dekho exist karta hai kya, phir use karo")

Operators JS ka **kaam karne ka tarika** hai — bina inke code sirf data ka collection hai, kuch hoga nahi!

---

## 2. 🏠 Real-World Analogies

### Analogy 1 — Logical Operators: _Security Guard System_

> **`&&` (AND)** = Building mein ghusne ke liye **ID card AND fingerprint** dono chahiye Ek bhi fail → andar nahi

> **`||` (OR)** = ATM mein **card OR mobile banking** se paise nikal sakte ho Koi ek kaam kare → done!

> **`??` (Nullish Coalescing)** = Online order mein address nahi diya? "Default address use karo" — sirf `null`/`undefined` pe hi fallback!

---

### Analogy 2 — Short Circuit: _Electricity Circuit_

> **`&&`** = Series circuit — ek wire cut → poori circuit band Pehla value falsy mila → aage check hi nahi karta!

> **`||`** = Parallel circuit — ek wire cut → doosri se current aata hai Pehla value truthy mila → aage check hi nahi karta!

---

## 3. 🔍 Core Concepts Breakdown

---

### 📌 PART 1: Arithmetic Operators

```javascript
// ============================================
// BASIC ARITHMETIC
// ============================================

console.log(10 + 3);   // 13  — Addition
console.log(10 - 3);   // 7   — Subtraction
console.log(10 * 3);   // 30  — Multiplication
console.log(10 / 3);   // 3.333... — Division
console.log(10 % 3);   // 1   — Modulus (remainder/baaki)
console.log(10 ** 3);  // 1000 — Exponentiation (10 ki power 3)

// ============================================
// MODULUS — Bahut useful operator!
// ============================================

// Even/Odd check:
console.log(10 % 2 === 0); // true  → Even
console.log(7  % 2 === 0); // false → Odd

// Circular/wrap-around logic:
const hours = 25;
console.log(hours % 24); // 1 — 25 ghante = 1 baje!

// Last N digits:
console.log(12345 % 100); // 45 — last 2 digits

// ============================================
// EXPONENTIATION (**)
// ============================================

console.log(2 ** 10);   // 1024 — binary mein common!
console.log(9 ** 0.5);  // 3    — square root (0.5 power = sqrt)
console.log(8 ** (1/3));// 2    — cube root

// ============================================
// UNARY OPERATORS — Ek hi operand pe kaam karte hain
// ============================================

let x = 5;

// Unary minus — sign flip karo
console.log(-x);   // -5
console.log(-(-x)); // 5

// Unary plus — type ko number mein convert karo!
console.log(+"42");    // 42    (string → number)
console.log(+true);    // 1     (boolean → number)
console.log(+false);   // 0
console.log(+null);    // 0
console.log(+"");      // 0
console.log(+"abc");   // NaN   (conversion fail)

// ============================================
// INCREMENT / DECREMENT — Pre vs Post
// ============================================

let a = 5;

// POST-increment: pehle VALUE return karo, phir badhao
console.log(a++); // 5  ← pehle 5 return hua
console.log(a);   // 6  ← ab 6 ho gaya

let b = 5;

// PRE-increment: pehle badhao, phir VALUE return karo
console.log(++b); // 6  ← pehle badha, phir return
console.log(b);   // 6

// Real difference matters in expressions:
let i = 3;
let result1 = i++ * 2; // 3 * 2 = 6 (pehle 3 use kiya, phir i=4)
console.log(result1);  // 6
console.log(i);        // 4

let j = 3;
let result2 = ++j * 2; // 4 * 2 = 8 (pehle j=4 kiya, phir 4 use kiya)
console.log(result2);  // 8
console.log(j);        // 4

// Decrement bhi same pattern:
let count = 10;
console.log(count--); // 10 (post — pehle return, phir ghata)
console.log(--count); // 8  (pre  — pehle ghata, phir return)
```

---

### 📌 PART 2: Comparison Operators

```javascript
// ============================================
// BASIC COMPARISONS
// ============================================

console.log(5 > 3);    // true
console.log(5 < 3);    // false
console.log(5 >= 5);   // true
console.log(5 <= 4);   // false

// == vs === (Chapter 4 se yaad hai?)
console.log(5 == "5");  // true  (coercion!)
console.log(5 === "5"); // false (strict — type bhi check)
console.log(5 != "5");  // false (coercion ke baad equal hai)
console.log(5 !== "5"); // true  (strict — alag types)

// String comparison — alphabetical (lexicographic) order!
console.log("apple" < "banana");  // true  ('a' < 'b')
console.log("Zebra" < "apple");   // true  (uppercase < lowercase!)
console.log("10" > "9");          // false! ("1" < "9" lexicographically)
console.log(10 > 9);              // true   (number comparison sahi)

// ============================================
// OBJECT COMPARISON — Why {} !== {} ?
// ============================================

const obj1 = { name: "Rahul" };
const obj2 = { name: "Rahul" };
const obj3 = obj1;

console.log(obj1 == obj2);   // false!
console.log(obj1 === obj2);  // false!
console.log(obj1 === obj3);  // true!

// WHY? Kyunki objects reference types hain!
// obj1 aur obj2 → ALAG addresses pe hain (content same, location alag)
// obj1 aur obj3 → SAME address point kar rahe hain

// Memory visualization:
// obj1 → [#A1F3]: { name: "Rahul" }
// obj2 → [#B2C4]: { name: "Rahul" }  ← Alag location!
// obj3 → [#A1F3]: { name: "Rahul" }  ← Same as obj1!

// obj1 === obj2 → #A1F3 === #B2C4 → false!
// obj1 === obj3 → #A1F3 === #A1F3 → true!

// Content compare karne ka sahi tarika:
console.log(JSON.stringify(obj1) === JSON.stringify(obj2)); // true ✅
```

---

### 📌 PART 3: Logical Operators — Asli Magic Yahan Hai!

```javascript
// ============================================
// && (AND) — Dono truthy hone chahiye
// ============================================

console.log(true && true);   // true
console.log(true && false);  // false
console.log(false && true);  // false
console.log(false && false); // false

// ============================================
// || (OR) — Ek bhi truthy kaafi hai
// ============================================

console.log(true || false);  // true
console.log(false || true);  // true
console.log(false || false); // false
console.log(true || true);   // true

// ============================================
// ! (NOT) — Ulta kar do
// ============================================

console.log(!true);  // false
console.log(!false); // true
console.log(!0);     // true  (0 falsy → !falsy = true)
console.log(!"");    // true  ("" falsy)
console.log(!"hi");  // false ("hi" truthy)

// !! — Double NOT (Boolean mein convert karo)
console.log(!!0);        // false
console.log(!!"hello");  // true
console.log(!!null);     // false
console.log(!![]);       // true (empty array truthy hai!)
console.log(!!{});       // true (empty object truthy hai!)
// !! === Boolean() casting ka shorthand!

// ============================================
// SHORT-CIRCUIT EVALUATION — Asli power!
// ============================================

// && → Pehla FALSY value return karta hai
//      Agar sab truthy → LAST value return karta hai
console.log(1 && 2 && 3);        // 3   (sab truthy → last)
console.log(1 && 0 && 3);        // 0   (0 falsy → yahan ruk gaya)
console.log(false && "hello");   // false (pehla hi falsy)
console.log("Rahul" && 42);      // 42  (dono truthy → last)

// || → Pehla TRUTHY value return karta hai
//      Agar sab falsy → LAST value return karta hai
console.log(0 || "" || "hello"); // "hello" (pehla truthy)
console.log(0 || false || null); // null (sab falsy → last)
console.log("Rahul" || "Priya"); // "Rahul" (pehla truthy)
console.log(0 || 42);            // 42

// ============================================
// PRACTICAL SHORT-CIRCUIT PATTERNS
// ============================================

// Pattern 1: Default value (|| use)
const userInput = "";
const displayName = userInput || "Anonymous"; // "" falsy → "Anonymous"
console.log(displayName); // "Anonymous"

// Pattern 2: Guard clause (&& use)
const user = { name: "Rahul", isAdmin: true };
user.isAdmin && console.log("Admin panel dikhao!"); // Runs!

const guest = { name: "Guest", isAdmin: false };
guest.isAdmin && console.log("Admin panel dikhao!"); // Nahi chala!

// Pattern 3: Function call guard
function riskyOperation() {
  console.log("Operation performed!");
  return true;
}
const shouldRun = false;
shouldRun && riskyOperation(); // Function hi nahi call hua!

// ============================================
// ?? (NULLISH COALESCING) — || se smarter!
// ============================================

// || → Koi bhi FALSY pe fallback
// ?? → Sirf null/undefined pe fallback!

const score = 0;

console.log(score || 100);  // 100 ← WRONG! 0 valid score hai!
console.log(score ?? 100);  // 0   ← CORRECT! 0 null/undefined nahi

const name1 = "";
console.log(name1 || "Default");  // "Default" (|| → "" bhi falsy)
console.log(name1 ?? "Default");  // "" (?? → "" null/undefined nahi!)

const notSet = null;
console.log(notSet ?? "Backup");  // "Backup" ✅

const alsoNotSet = undefined;
console.log(alsoNotSet ?? "Backup"); // "Backup" ✅

// Real world example:
function getUserScore(user) {
  // || se galti hogi agar score 0 ho!
  // return user.score || "No score"; // ❌

  return user.score ?? "No score"; // ✅ Sahi!
}

console.log(getUserScore({ score: 0 }));    // 0   ← Correct!
console.log(getUserScore({ score: null })); // "No score" ← Correct!
console.log(getUserScore({ score: 95 }));   // 95  ← Correct!
```

---

### 📌 PART 4: Assignment Operators

```javascript
// ============================================
// BASIC ASSIGNMENT
// ============================================

let x = 10;       // Simple assignment

// Compound assignment (shorthand):
x += 5;   // x = x + 5  → 15
x -= 3;   // x = x - 3  → 12
x *= 2;   // x = x * 2  → 24
x /= 4;   // x = x / 4  → 6
x %= 4;   // x = x % 4  → 2
x **= 3;  // x = x ** 3 → 8

console.log(x); // 8

// ============================================
// LOGICAL ASSIGNMENT — ES2021 ka naya gift!
// ============================================

// &&= → Sirf tab assign karo jab LEFT side TRUTHY ho
let a = 1;
a &&= 99;         // a truthy (1) hai → 99 assign karo
console.log(a);   // 99

let b = 0;
b &&= 99;         // b falsy (0) hai → kuch mat karo
console.log(b);   // 0 (unchanged!)

// ||= → Sirf tab assign karo jab LEFT side FALSY ho
let c = 0;
c ||= 42;         // c falsy → 42 assign karo
console.log(c);   // 42

let d = "hello";
d ||= "default";  // d truthy → kuch mat karo
console.log(d);   // "hello" (unchanged!)

// ??= → Sirf tab assign karo jab LEFT side null/undefined ho
let e = null;
e ??= "fallback"; // null → assign karo
console.log(e);   // "fallback"

let f = 0;
f ??= "fallback"; // 0 → null/undefined nahi → mat badlo
console.log(f);   // 0 (unchanged!)

// Real world use:
const config = {};
config.timeout ??= 3000;    // Set only if not already set
config.retries ??= 3;
config.debug   ||= false;
console.log(config); // { timeout: 3000, retries: 3, debug: false }
```

---

### 📌 PART 5: Special Operators — Ye Sab Bahut Kaam Ke Hain!

```javascript
// ============================================
// typeof — Runtime type check
// ============================================

console.log(typeof 42);          // "number"
console.log(typeof "hello");     // "string"
console.log(typeof true);        // "boolean"
console.log(typeof undefined);   // "undefined"
console.log(typeof null);        // "object" ← bug!
console.log(typeof {});          // "object"
console.log(typeof []);          // "object" ← bug!
console.log(typeof function(){}); // "function"
console.log(typeof Symbol());    // "symbol"
console.log(typeof 42n);         // "bigint"

// typeof undeclared variable → error nahi! "undefined" deta hai
console.log(typeof undeclaredVar); // "undefined" (safe!)

// ============================================
// instanceof — Prototype chain check
// ============================================

const arr = [1, 2, 3];
const obj = {};
const date = new Date();

console.log(arr instanceof Array);   // true
console.log(arr instanceof Object);  // true! (Array Object ka child hai)
console.log(obj instanceof Object);  // true
console.log(date instanceof Date);   // true
console.log(date instanceof Object); // true

// typeof vs instanceof:
console.log(typeof arr);          // "object" (specific nahi!)
console.log(arr instanceof Array); // true   (specific! ✅)

// ============================================
// in — Property existence check
// ============================================

const person = {
  name: "Rahul",
  age: 25,
  city: undefined  // Value undefined hai lekin key EXISTS hai!
};

console.log("name" in person);   // true
console.log("age" in person);    // true
console.log("city" in person);   // true  ← Key hai, value undefined
console.log("email" in person);  // false ← Key hi nahi!

// vs hasOwnProperty:
console.log(person.hasOwnProperty("name")); // true
console.log("toString" in person);          // true! (inherited)
console.log(person.hasOwnProperty("toString")); // false (inherited nahi)

// Array mein 'in' = index check:
const fruits = ["apple", "banana", "mango"];
console.log(0 in fruits);  // true  (index 0 exist karta hai)
console.log(3 in fruits);  // false (index 3 nahi hai)
console.log("apple" in fruits); // false! (value nahi, index check hota!)

// ============================================
// delete — Object property hatao
// ============================================

const user = { name: "Rahul", age: 25, temp: "delete me" };

console.log(user);           // { name, age, temp }
delete user.temp;
console.log(user);           // { name, age }
console.log("temp" in user); // false ✅

// delete returns true/false:
console.log(delete user.name);      // true (deleted)
console.log(delete user.nonExist);  // true (already didn't exist)

// delete array element → hole create hota hai!
const arr2 = [1, 2, 3, 4];
delete arr2[1];
console.log(arr2);        // [1, empty, 3, 4] ← Hole!
console.log(arr2.length); // 4 (length nahi ghata!)
// Better: splice use karo delete ki jagah arrays mein

// ============================================
// ?. (Optional Chaining) — Safety net!
// ============================================

const userProfile = {
  name: "Rahul",
  address: {
    city: "Delhi"
  }
};

// Without optional chaining — DANGEROUS:
// console.log(userProfile.contact.phone); // ❌ TypeError!

// With optional chaining — SAFE:
console.log(userProfile?.address?.city);   // "Delhi" ✅
console.log(userProfile?.contact?.phone);  // undefined (no error!) ✅
console.log(userProfile?.address?.pincode); // undefined ✅

// Optional chaining with methods:
const str = "hello";
console.log(str?.toUpperCase()); // "HELLO"
console.log(null?.toUpperCase()); // undefined (no error!)

// Optional chaining with arrays:
const data = { users: ["Rahul", "Priya"] };
console.log(data?.users?.[0]);     // "Rahul"
console.log(data?.posts?.[0]);     // undefined (posts nahi hai)

// Real world API response handling:
function displayUserCity(apiResponse) {
  // Pehle wala style (bahut verbose):
  // if (apiResponse && apiResponse.data &&
  //     apiResponse.data.user && apiResponse.data.user.address) {
  //   return apiResponse.data.user.address.city;
  // }

  // Optional chaining se — clean!
  return apiResponse?.data?.user?.address?.city ?? "City unavailable";
}

// ============================================
// TERNARY OPERATOR ? : — If-else ka shorthand
// ============================================

const age = 20;

// Normal if-else:
// if (age >= 18) {
//   console.log("Adult");
// } else {
//   console.log("Minor");
// }

// Ternary — ek line mein!
const status = age >= 18 ? "Adult" : "Minor";
console.log(status); // "Adult"

// Ternary mein expressions use karo:
const score = 75;
const grade = score >= 90 ? "A" : score >= 75 ? "B" : score >= 60 ? "C" : "F";
console.log(grade); // "B"

// ⚠️ Warning: Zyada nested ternary mat karo — unreadable hota hai!
// Iss case mein if-else ya lookup object better hai:
const gradeMap = { A: [90, 100], B: [75, 89], C: [60, 74] };

// ============================================
// SPREAD (...) — Expand karo
// ============================================

// Arrays spread:
const arr1 = [1, 2, 3];
const arr2 = [4, 5, 6];
const combined = [...arr1, ...arr2]; // [1, 2, 3, 4, 5, 6]
console.log(combined);

// Array copy (shallow):
const original = [1, 2, 3];
const copy = [...original];   // Naya array!
copy.push(4);
console.log(original);        // [1, 2, 3] ← Safe!

// Object spread:
const defaults = { theme: "dark", lang: "en", size: 14 };
const userPrefs = { theme: "light", size: 16 };   // Override karo

const finalConfig = { ...defaults, ...userPrefs };
// Later wala same key override karta hai!
console.log(finalConfig);
// { theme: "light", lang: "en", size: 16 }

// Function arguments mein spread:
const nums = [5, 2, 8, 1, 9];
console.log(Math.max(...nums)); // 9 (array spread as arguments)
console.log(Math.min(...nums)); // 1

// ============================================
// REST (...) — Collect karo (Spread ka ulta!)
// ============================================

// Function parameters mein:
function sum(...numbers) {       // Saare args ek array mein!
  return numbers.reduce((acc, n) => acc + n, 0);
}
console.log(sum(1, 2, 3));       // 6
console.log(sum(1, 2, 3, 4, 5)); // 15

// Mixed parameters:
function logInfo(first, second, ...rest) {
  console.log("First:", first);
  console.log("Second:", second);
  console.log("Rest:", rest);    // Array of remaining
}
logInfo("a", "b", "c", "d", "e");
// First: "a", Second: "b", Rest: ["c", "d", "e"]

// Destructuring mein rest:
const [head, ...tail] = [1, 2, 3, 4, 5];
console.log(head); // 1
console.log(tail); // [2, 3, 4, 5]

const { name, ...otherProps } = { name: "Rahul", age: 25, city: "Delhi" };
console.log(name);       // "Rahul"
console.log(otherProps); // { age: 25, city: "Delhi" }
```

---

### 📌 PART 6: Bitwise Operators — Binary Level Operations

```javascript
// ============================================
// BITWISE — Numbers ko binary mein treat karo
// ============================================

// Numbers binary mein:
// 5  = 0101
// 3  = 0011
// 12 = 1100

// & (AND) — Dono bits 1 hone chahiye
console.log(5 & 3);  // 0101 & 0011 = 0001 = 1

// | (OR) — Koi ek bit 1 ho
console.log(5 | 3);  // 0101 | 0011 = 0111 = 7

// ^ (XOR) — Exactly ek bit 1 ho (different)
console.log(5 ^ 3);  // 0101 ^ 0011 = 0110 = 6

// ~ (NOT/Bitwise complement) — Sab bits flip karo
console.log(~5);     // -(5+1) = -6 (two's complement!)

// << (Left shift) — Bits left shift, zeros add
console.log(5 << 1); // 0101 → 1010 = 10 (×2)
console.log(5 << 2); // 0101 → 10100 = 20 (×4)

// >> (Right shift) — Bits right shift (sign preserve)
console.log(20 >> 1); // 10100 → 01010 = 10 (÷2)
console.log(20 >> 2); // 10100 → 00101 = 5  (÷4)

// >>> (Unsigned right shift) — Sign bit ko bhi shift karo
console.log(-1 >>> 0); // 4294967295 (32-bit max!)

// ============================================
// PRACTICAL BITWISE USE CASES
// ============================================

// 1. Even/Odd check (faster than %)
const isEven = n => (n & 1) === 0;
const isOdd  = n => (n & 1) === 1;
console.log(isEven(4)); // true
console.log(isOdd(7));  // true

// 2. Powers of 2 check
const isPowerOf2 = n => n > 0 && (n & (n - 1)) === 0;
console.log(isPowerOf2(16)); // true  (16 = 2^4)
console.log(isPowerOf2(12)); // false

// 3. Swap without temp variable (XOR trick!)
let p = 5, q = 10;
p = p ^ q;   // p = 5^10 = 15
q = p ^ q;   // q = 15^10 = 5
p = p ^ q;   // p = 15^5 = 10
console.log(p, q); // 10, 5 — swapped! ✅

// 4. Math.floor shorthand (positive numbers ke liye)
console.log(~~3.7);   // 3 (double bitwise NOT)
console.log(7.9 | 0); // 7 (OR with 0)
// Note: Sirf positive numbers pe reliable!

// 5. Permission/Flag system (real use!)
const READ    = 0b001; // 1
const WRITE   = 0b010; // 2
const EXECUTE = 0b100; // 4

// Permissions combine karo:
const adminPermissions = READ | WRITE | EXECUTE; // 7 = 111
const userPermissions  = READ | WRITE;            // 3 = 011

// Check karo:
const canRead    = (userPermissions & READ)    !== 0; // true
const canExecute = (userPermissions & EXECUTE) !== 0; // false!

console.log(`Can read: ${canRead}`);       // true
console.log(`Can execute: ${canExecute}`); // false
```

---

## 4. 💻 Complete Code Example — Sab Operators Ek Saath

```javascript
"use strict";

// ============================================
// REAL SCENARIO: E-Commerce Price Calculator
// Saare operators use honge!
// ============================================

const PriceCalculator = {

  // ============================================
  // Config with Nullish + Logical Assignment
  // ============================================
  config: {
    taxRate: null,      // Not set yet
    discount: 0,        // Set lekin 0 (valid!)
    maxItems: undefined // Not set
  },

  init() {
    // ??= → Sirf null/undefined pe set karo
    this.config.taxRate  ??= 0.18;
    this.config.maxItems ??= 10;

    // ||= → Falsy pe default (0 bhi replace hoga — careful!)
    // this.config.discount ||= 5; // ← 0 bhi replace ho jaata! Bad!
    // ??= use karo discount ke liye:
    this.config.discount ??= 5;   // 0 valid hai, so unchanged

    console.log(
      "%c⚙️ CONFIG %cInitialized!",
      "background:#455a64;color:#cfd8dc;padding:2px 8px;" +
      "border-radius:3px 0 0 3px;font-weight:bold;",
      "background:#eceff1;color:#263238;padding:2px 8px;" +
      "border-radius:0 3px 3px 0;"
    );
    console.table(this.config);
  },

  // ============================================
  // Calculate price with all operator types
  // ============================================
  calculate(items = [], couponCode = null) {

    // instanceof check
    if (!(items instanceof Array)) {
      console.log(
        "%c❌ ERROR %cItems must be an array!",
        "background:#d50000;color:white;padding:2px 8px;" +
        "border-radius:3px 0 0 3px;",
        "background:#ffebee;color:#b71c1c;padding:2px 8px;" +
        "border-radius:0 3px 3px 0;"
      );
      return null;
    }

    // Spread to avoid mutation + Array operators
    const validItems = [...items].filter(item =>
      // Optional chaining + typeof check
      typeof item?.price === "number" &&
      item.price > 0 &&            // Comparison
      item?.quantity > 0           // Optional chain + comparison
    );

    // Rest in destructuring
    const [firstItem, ...restItems] = validItems;

    // Short circuit — agar koi items nahi
    if (!validItems.length) {
      return { total: 0, message: "Cart is empty!" };
    }

    // Arithmetic operators
    let subtotal = validItems.reduce((acc, item) => {
      const itemTotal = item.price * item.quantity; // *
      return acc + itemTotal;                         // +
    }, 0);

    // Modulus use — Bulk discount logic!
    // Agar 3 se divisible items count → extra 5% off
    const bulkBonus = (validItems.length % 3 === 0) ? 0.05 : 0;

    // Coupon discount (nullish coalescing)
    const coupons = { SAVE10: 0.10, SALE20: 0.20, VIP50: 0.50 };
    const couponDiscount = coupons[couponCode] ?? 0; // No coupon → 0

    // Bitwise for rounding (internal calculation)
    const totalDiscount = couponDiscount + bulkBonus + this.config.discount;

    // Exponentiation — compound discount apply
    // (1 - discount)^1 simplified:
    const afterDiscount = subtotal * (1 - totalDiscount);
    const tax           = afterDiscount * this.config.taxRate;
    const total         = afterDiscount + tax;

    // Ternary for free shipping
    const shippingFee   = total > 500 ? 0 : 50;
    const grandTotal    = total + shippingFee;

    return {
      subtotal:      +subtotal.toFixed(2),     // Unary + to ensure number
      discount:      +(totalDiscount * 100).toFixed(1),
      tax:           +tax.toFixed(2),
      shipping:      shippingFee,
      grandTotal:    +grandTotal.toFixed(2),
      freeShipping:  shippingFee === 0,        // Comparison → boolean
      itemCount:     validItems.length,
      bulkBonus:     bulkBonus > 0             // Comparison → boolean
    };
  },

  // ============================================
  // Display with styled logs
  // ============================================
  display(result) {
    // Optional chaining — agar result null ho
    if (!result?.grandTotal && result?.grandTotal !== 0) {
      return;
    }

    console.log(
      "%c🛒 BILL SUMMARY",
      "background:#4a148c;color:#ea80fc;padding:4px 12px;" +
      "border-radius:4px;font-size:14px;font-weight:bold;"
    );

    // Logical AND for conditional display
    result.bulkBonus && console.log(
      "%c🎁 BONUS %cBulk discount applied! 5% extra off",
      "background:#00897b;color:white;padding:2px 8px;" +
      "border-radius:3px 0 0 3px;",
      "background:#e0f2f1;color:#004d40;padding:2px 8px;" +
      "border-radius:0 3px 3px 0;"
    );

    result.freeShipping && console.log(
      "%c🚚 FREE %cFree Shipping!",
      "background:#1565c0;color:white;padding:2px 8px;" +
      "border-radius:3px 0 0 3px;",
      "background:#e3f2fd;color:#0d47a1;padding:2px 8px;" +
      "border-radius:0 3px 3px 0;"
    );

    console.table({
      "Subtotal":    `₹${result.subtotal}`,
      "Discount":    `${result.discount}%`,
      "Tax (18%)":   `₹${result.tax}`,
      "Shipping":    result.freeShipping ? "FREE 🚚" : `₹${result.shipping}`,
      "GRAND TOTAL": `₹${result.grandTotal}`
    });
  }
};

// ============================================
// TEST IT!
// ============================================
PriceCalculator.init();

const cartItems = [
  { name: "Laptop",   price: 45000, quantity: 1 },
  { name: "Mouse",    price: 800,   quantity: 2 },
  { name: "Keyboard", price: 1200,  quantity: 1 },
  { name: null,       price: -100,  quantity: 1 }, // Invalid — filter hoga!
];

const result = PriceCalculator.calculate(cartItems, "SAVE10");
PriceCalculator.display(result);
```

---

## 5. ⚠️ Common Mistakes

```javascript
// ❌ MISTAKE 1: || vs ?? confusion
const userScore = 0;
const display1 = userScore || "No score"; // "No score" ← WRONG!
const display2 = userScore ?? "No score"; // 0 ← CORRECT!

// ❌ MISTAKE 2: Pre vs Post increment confusion
let a = 5;
let b = a++ + 1;  // b = 5+1 = 6 (a pehle use hua, phir increment)
let c = ++a + 1;  // a ab 7 hai, c = 7+1 = 8

// ❌ MISTAKE 3: Object comparison
const o1 = { x: 1 };
const o2 = { x: 1 };
if (o1 === o2) { /* Kabhi nahi chalega! */ }
// ✅ Fix:
if (JSON.stringify(o1) === JSON.stringify(o2)) { }

// ❌ MISTAKE 4: delete array elements
const arr = [1, 2, 3, 4];
delete arr[1];           // [1, empty, 3, 4] — Hole!
// ✅ Fix:
arr.splice(1, 1);        // [1, 3, 4] — Clean removal

// ❌ MISTAKE 5: Optional chaining without null check at top
const data = null;
const name = data?.user?.name ?? "Unknown"; // ✅ Safe
// data.user?.name → ❌ TypeError! (data khud null hai)

// ❌ MISTAKE 6: Spread shallow copy samajhna deep copy
const nested = { user: { name: "Rahul" } };
const copy   = { ...nested };
copy.user.name = "Priya";
console.log(nested.user.name); // "Priya" — original badla! 😱
// ✅ Fix: structuredClone(nested)

// ❌ MISTAKE 7: typeof null
if (typeof myVar === "object") {
  myVar.doSomething(); // ❌ null bhi "object" hai!
}
// ✅ Fix:
if (myVar !== null && typeof myVar === "object") { }

// ❌ MISTAKE 8: Ternary ko statement ki jagah use karna
// age >= 18 ? console.log("Adult") : console.log("Minor"); // Works but ugly
// ✅ If-else hi use karo side effects ke liye
// ✅ Ternary sirf VALUE return ke liye:
const label = age >= 18 ? "Adult" : "Minor";
```

---

## 6. 🧠 Mini Quiz

Q1. Short Circuit:

Yeh expressions kya return karenge?

```javascript
console.log(0 || "" || null || "Found!");
console.log(1 && 2 && 0 && 4);
console.log(null ?? undefined ?? 0 ?? "last");
console.log(false || 0 || "" || null);
```

Q2. Pre/Post Increment:

`x`, `y`, `z` ki final values kya hongi?

```javascript
let x = 5;
let y = x++ * 2;
let z = ++x * 2;
```

Q3. Operator Choice:

User ka `volume` setting store hai — value `0` ho sakti hai (mute). Default `50` tab lagao jab value set hi nahi hui ho (`null`/`undefined`). Kaunsa operator use karoge aur kyun?

Q4. Spread vs Rest:

Yeh dono `...` alag hain — kaise? Example do.

Q5. Practical — Bug Dhundo:

```javascript
const settings = { notifications: false };
settings.notifications ||= true;
console.log(settings.notifications); // Expected: false, Got: ???
```

Kya output aayega aur kyun? Fix karo.

✅ Answers (pehle khud try karo!)

**A1:**

- `"Found!"` (pehla truthy)
- `0` (pehla falsy — `&&` ruk gaya)
- `0` (`??` sirf null/undefined check karta hai — 0 valid hai!)
- `null` (sab falsy — `||` last value return karta hai)

**A2:** `y = 10` (x=5 use kiya → x=6), `z = 14` (x=7 hua → 7×2)

**A3:** `??=` use karo — kyunki `0` (mute) valid value hai. `||=` galat hai kyunki `0` falsy hai aur override ho jaayega!

**A4:** Spread = expand karta hai (`...arr` function call ya new array mein). Rest = collect karta hai (`function(...args)` mein remaining args gather karna).

**A5:** Output: `true`! Bug: `||=` ne `false` ko falsy maana aur `true` assign kar diya. Fix: `settings.notifications ??= true` — tab hi set karo jab `null`/`undefined` ho.


---

## 7. 🛠️ Hands-on Task

### Task: "Operator Toolkit" 🔧

Teen utility functions banao:

**Part A — Smart Default:**

```javascript
// Ek function banao jo properly defaults handle kare
// ?? aur ||= aur ??= use karo

function createUserConfig(options) {
  // Expected behavior:
  // - name: required (error if missing)
  // - theme: default "light" (but "dark" valid, "" bhi valid!)
  // - volume: default 50 (but 0 valid — mute!)
  // - notifications: default true (but false valid!)
  // - maxRetries: default 3
}

createUserConfig({ name: "Rahul", volume: 0, notifications: false });
// Should output: { name: "Rahul", theme: "light", volume: 0,
//                  notifications: false, maxRetries: 3 }
```

**Part B — Permission System:**

```javascript
// Bitwise permissions system banao
// READ=1, WRITE=2, EXECUTE=4, DELETE=8, ADMIN=16

const Permissions = {
  READ: 0b00001,
  WRITE: 0b00010,
  EXECUTE: 0b00100,
  DELETE: 0b01000,
  ADMIN: 0b10000,

  grant(currentPerms, ...newPerms) { /* | use karo */ },
  revoke(currentPerms, ...removePerms) { /* & ~ use karo */ },
  has(currentPerms, permission) { /* & use karo */ },
  listAll(currentPerms) { /* Sab permissions list karo */ }
};

// Usage:
let userPerms = Permissions.grant(0, Permissions.READ, Permissions.WRITE);
console.log(Permissions.has(userPerms, Permissions.READ));    // true
console.log(Permissions.has(userPerms, Permissions.EXECUTE)); // false
userPerms = Permissions.revoke(userPerms, Permissions.WRITE);
console.log(Permissions.listAll(userPerms));                  // ["READ"]
```

**Part C — Safe Data Accessor:**

```javascript
// Optional chaining + ?? use karke
// Deeply nested data safely access karo

function safeGet(obj, path, defaultValue = undefined) {
  // path = "user.address.city" string ho
  // obj?.user?.address?.city jaisa behavior chahiye
  // Bina eval ke!
}

const data = { user: { profile: { name: "Rahul" } } };
safeGet(data, "user.profile.name");      // "Rahul"
safeGet(data, "user.address.city");      // undefined
safeGet(data, "user.address.city", "N/A"); // "N/A"
```

---

## 8. 🏗️ Project-Based Learning

### Mini Project: **"Smart Shopping Cart with Coupon Engine"** 🛒

```
Features:
✅ Items add/remove (spread for immutability)
✅ Quantity update (arithmetic operators)
✅ Multiple coupon codes (nullish coalescing)
✅ Volume discount (modulus + ternary)
✅ Permission system (bitwise) — Admin/User/Guest views
✅ Safe property access (optional chaining)
✅ Bulk discount (short circuit evaluation)
✅ Auto tax calculation (compound assignment)
✅ Styled console output
```

**Data Structure:**

```javascript
const Cart = {
  items: [],
  user: { role: "user", permissions: 0 },  // Bitwise permissions
  config: { tax: null, maxQty: null },       // ??= se set karo

  add(item) { /* ...spread, validation */ },
  remove(id) { /* filter */ },
  updateQty(id, delta) { /* += with bounds */ },
  applyCoupon(code) { /* ?? fallback */ },
  getTotal() { /* arithmetic + ternary */ },
  display() { /* optional chaining + styled logs */ }
};
```

---

_Koi bhi operator confuse kare — especially `??` vs `||`, ya spread vs rest — seedha poochho! Yeh operators modern JS code mein har jagah milenge!_ 🚀

