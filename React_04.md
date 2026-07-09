# useId Hook

## Introduction

`useId` React ka Hook hai jo unique ID generate karne ke liye use hota hai.

Ye mostly form elements ko connect karne ke liye use kiya jata hai, jaise:

- Label aur Input ko connect karna
- Accessibility improve karna
- Duplicate IDs se bachna

---

# Problem Without useId

```jsx
<label htmlFor="name">Name</label>
<input id="name" />
```

Agar same component multiple times render ho jaye to:

```html
<input id="name" />
<input id="name" />
<input id="name" />
```

❌ Duplicate IDs create ho jayengi.

---

# Solution Using useId

```jsx
import { useId } from "react";

function App() {

    const id = useId();

    return (
        <>
            <label htmlFor={id}>
                Name
            </label>

            <input id={id} />
        </>
    );
}
```

---

# Example

```jsx
import { useId } from "react";

function LoginForm() {

    const id = useId();

    return (
        <>
            <label htmlFor={id}>
                Username
            </label>

            <input id={id} />
        </>
    );
}
```

---

# Output

React internally kuch aisi unique ID generate karega:

```text
:r0:
```

Ya

```text
:r1:
```

Ya

```text
:r2:
```

Har component ke liye alag ID hogi.

---

# Multiple IDs

```jsx
import { useId } from "react";

function App() {

    const id = useId();

    return (
        <>
            <label htmlFor={`${id}-name`}>
                Name
            </label>

            <input id={`${id}-name`} />

            <label htmlFor={`${id}-email`}>
                Email
            </label>

            <input id={`${id}-email`} />
        </>
    );
}
```

---

# Real Use Case

### Form Fields

```jsx
<label htmlFor={id}>
    Email
</label>

<input id={id} />
```

---

### Accessibility

Screen readers label aur input ka relation easily samajh pate hain.

---

# Important Points

- `useId()` unique ID generate karta hai.
- Mostly forms me use hota hai.
- Accessibility improve karta hai.
- Duplicate IDs ki problem solve karta hai.
- React 18 aur React 19 dono me available hai.

---

# Syntax

```jsx
const id = useId();
```

---

# Summary

- `useId` unique ID generate karne ke liye use hota hai.
- Label aur Input ko connect karne me helpful hai.
- Accessibility improve karta hai.
- Duplicate IDs se bachata hai.
- Forms me sabse zyada use kiya jata hai.

# React Router 7

## Introduction

React Router 7 ek library hai jo React application me **Routing** implement karne ke liye use hoti hai.

Routing ka matlab hota hai:

> Different URLs ke according different Components ya Pages show karna.

Example:

```text
/           → Home Page
/about      → About Page
/contact    → Contact Page
/profile    → Profile Page
```

React khud routing provide nahi karta, isliye React Router use kiya jata hai.

---

# Why React Router?

Without React Router:

```text
Har Page Change Par Browser Reload Hoga
```

With React Router:

```text
Page Reload Nahi Hoga
Sirf Component Change Hoga
```

Isliye React Router SPA (Single Page Application) banane me help karta hai.

---

# Installation

```bash
npm install react-router
```

Ya

```bash
npm install react-router-dom
```

---

# Basic Example

## Home Component

```jsx
function Home() {
    return <h1>Home Page</h1>;
}
```

---

## About Component

```jsx
function About() {
    return <h1>About Page</h1>;
}
```

---

## App.jsx

```jsx
import {
    BrowserRouter,
    Routes,
    Route
} from "react-router-dom";

function App() {
    return (
        <BrowserRouter>
            <Routes>

                <Route
                    path="/"
                    element={<Home />}
                />

                <Route
                    path="/about"
                    element={<About />}
                />

            </Routes>
        </BrowserRouter>
    );
}
```

---

# Important Components

## BrowserRouter

Application me routing enable karta hai.

```jsx
<BrowserRouter>
    <App />
</BrowserRouter>
```

---

## Routes

Saare routes ko wrap karta hai.

```jsx
<Routes>
    ...
</Routes>
```

---

## Route

Kis URL par kaunsa component show hoga ye define karta hai.

```jsx
<Route
    path="/about"
    element={<About />}
/>
```

---

# Navigation

Page change karne ke liye `Link` use karte hain.

```jsx
import { Link } from "react-router-dom";

function Navbar() {
    return (
        <>
            <Link to="/">Home</Link>

            <Link to="/about">
                About
            </Link>
        </>
    );
}
```

---

# Nested Route Example

```jsx
<Route path="/dashboard">

    <Route
        path="profile"
        element={<Profile />}
    />

    <Route
        path="settings"
        element={<Settings />}
    />

</Route>
```

URLs:

```text
/dashboard/profile
/dashboard/settings
```

---

# Dynamic Route

```jsx
<Route
    path="/user/:id"
    element={<User />}
/>
```

URL:

```text
/user/101
/user/102
```

Component me ID access:

```jsx
import { useParams } from "react-router-dom";

function User() {

    const { id } = useParams();

    return <h1>User ID: {id}</h1>;
}
```

---

# React Router 7 Features

- Client Side Routing
- Nested Routing
- Dynamic Routing
- Route Parameters
- Navigation Without Reload
- Layout Routes
- Data Loading
- Error Handling
- Better Performance

---

# Common Hooks

### useNavigate

Page redirect karne ke liye.

```jsx
const navigate = useNavigate();

navigate("/about");
```

---

### useParams

Route parameters lene ke liye.

```jsx
const { id } = useParams();
```

---

### useLocation

Current URL information ke liye.

```jsx
const location = useLocation();
```

---

# Flow

```text
User Clicks Link
        ↓
URL Change
        ↓
React Router Match Route
        ↓
Required Component Render
```

---

# Summary

- React Router 7 React applications me routing ke liye use hota hai.
- Different URLs par different components show karta hai.
- Page reload ke bina navigation provide karta hai.
- Main Components:
  - BrowserRouter
  - Routes
  - Route
  - Link
- Main Hooks:
  - useNavigate
  - useParams
  - useLocation
- SPA (Single Page Application) development ke liye bahut important library hai.