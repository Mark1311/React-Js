# dependencies vs devDependencies

| Feature | dependencies | devDependencies |
|----------|-------------|----------------|
| Use | Production me bhi required hoti hain | Sirf Development ke time required hoti hain |
| Install Command | `npm install package-name` | `npm install -D package-name` |
| Production Build | ✅ Install hoti hain | ❌ Install nahi hoti |
| Example | React, React DOM, Axios | Vite, ESLint, Prettier |

## dependencies Example

```bash
npm install axios
```

```json
{
  "dependencies": {
    "axios": "^1.0.0"
  }
}
```

> App chalane ke liye required hai.

---

## devDependencies Example

```bash
npm install -D eslint
```

```json
{
  "devDependencies": {
    "eslint": "^9.0.0"
  }
}
```

> Sirf development ke liye required hai.

## Summary

- `dependencies` → Application run karne ke liye zaruri packages.
- `devDependencies` → Development tools wale packages.

# Variable vs State

React me beginners ko sabse zyada confusion Variable aur State me hoti hai.

Simple rule:

> Agar value UI me show ho rahi hai aur uske change hone par UI bhi update karni hai, to State use karo.

---

## Variable

Variable normal JavaScript variable hota hai.

```jsx
let count = 0;
```

React is variable ko track nahi karta.

### Example

```jsx
function App() {

    let count = 0;

    const increment = () => {
        count++;
        console.log(count);
    };

    return (
        <>
            <h1>{count}</h1>

            <button onClick={increment}>
                Increment
            </button>
        </>
    );
}
```

### Output

Button click:

```text
Console:
1
2
3
4
```

Screen:

```text
0
```

### Why?

Kyuki variable change hua hai, lekin React ko pata hi nahi chala ki UI update karni hai.

---

## State

State React ka special data hota hai.

```jsx
const [count, setCount] = useState(0);
```

React State ko track karta hai.

### Example

```jsx
import { useState } from "react";

function App() {

    const [count, setCount] = useState(0);

    return (
        <>
            <h1>{count}</h1>

            <button
                onClick={() => setCount(count + 1)}
            >
                Increment
            </button>
        </>
    );
}
```

### Output

Button click:

```text
1
2
3
4
```

Screen:

```text
1
2
3
4
```

### Why?

Kyuki State update hui.

```jsx
setCount(count + 1);
```

React ne component ko re-render kar diya.

---

## Real Difference

### Variable

```jsx
let name = "Bittu";
```

Value change:

```jsx
name = "Kumar";
```

Result:

```text
UI Update Nahi Hogi
```

---

### State

```jsx
const [name, setName] = useState("Bittu");
```

Value change:

```jsx
setName("Kumar");
```

Result:

```text
UI Update Ho Jayegi
```

---

## Flow

### Variable

```text
Value Change
    ↓
React Ko Pata Nahi Chala
    ↓
No Re-render
    ↓
UI Same
```

---

### State

```text
State Change
    ↓
React Notice Karta Hai
    ↓
Component Re-render
    ↓
UI Update
```

---

## Interview Style Line

> State React dwara managed data hota hai jo change hone par component ko re-render karta hai, jabki Variable normal JavaScript data hota hai jise React track nahi karta.

---

## Summary

| Variable | State |
|-----------|--------|
| JavaScript ka normal variable | React ka special data |
| React track nahi karta | React track karta hai |
| UI update nahi hoti | UI update hoti hai |
| Re-render nahi hota | Re-render hota hai |
| `let`, `const` se banta hai | `useState()` se banti hai |

### Yaad Rakhne Ki Trick

```text
Variable → Data Change
State    → Data + UI Change
```

# React Version Numbers (0.0.0) Ka Matlab

React aur dusre packages **Semantic Versioning (SemVer)** follow karte hain.

Format:

```text
MAJOR.MINOR.PATCH
```

Example:

```text
19.1.0
│  │  │
│  │  └── PATCH
│  └───── MINOR
└──────── MAJOR
```

---

## 1. MAJOR Version

Example:

```text
18.0.0 → 19.0.0
```

### Matlab

- Bade Changes
- Breaking Changes ho sakte hain
- Purana code break ho sakta hai

Example:

```text
React 18 → React 19
```

---

## 2. MINOR Version

Example:

```text
19.0.0 → 19.1.0
```

### Matlab

- New Features Add Hui
- Purana Code Normally Chalega
- Breaking Changes Nahi Hoti

---

## 3. PATCH Version

Example:

```text
19.1.0 → 19.1.1
```

### Matlab

- Bug Fixes
- Security Fixes
- Performance Improvements

---

## Examples

### React 19.0.0

```text
Major Release
```

---

### React 19.1.0

```text
New Feature Added
```

---

### React 19.1.1

```text
Bug Fixed
```

---

## Easy Trick

```text
19 . 1 . 1
│    │   │
│    │   └─ Bug Fix
│    └───── New Feature
└────────── Major Change
```

## Summary

| Part | Meaning |
|--------|----------|
| MAJOR | Breaking Changes |
| MINOR | New Features |
| PATCH | Bug Fixes |

### Example

```text
18.2.1

18 = Major Version
2  = Minor Version
1  = Patch Version
```

# Ternary Operator

## Introduction

Ternary Operator JavaScript ka short form of `if...else` hai.

Jab simple condition check karni ho, tab Ternary Operator use karte hain.

---

## Syntax

```javascript
condition ? trueValue : falseValue
```

---

## Example

```javascript
let age = 20;

let result = age >= 18 ? "Adult" : "Minor";

console.log(result);
```

### Output

```text
Adult
```

---

## if...else vs Ternary

### if...else

```javascript
let age = 20;

if (age >= 18) {
    console.log("Adult");
} else {
    console.log("Minor");
}
```

### Ternary

```javascript
let age = 20;

console.log(
    age >= 18 ? "Adult" : "Minor"
);
```

---

## React Example

```jsx
function App() {

    const isLogin = true;

    return (
        <h1>
            {isLogin ? "Welcome User" : "Please Login"}
        </h1>
    );
}
```

### Output

```text
Welcome User
```

---

## Easy Understanding

```javascript
10 > 5
    ? "True"
    : "False"
```

Condition True:

```text
True
```

Condition False:

```text
False
```

---

## Summary

- Ternary Operator `if...else` ka short form hai.
- Syntax:

```javascript
condition ? trueValue : falseValue
```

- React me conditional rendering ke liye bahut use hota hai.
- Simple conditions ke liye best hai.

