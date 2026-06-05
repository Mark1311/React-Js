# What is React JS?

## Introduction

React JS ek **JavaScript Library** hai jo **User Interface (UI)** banane ke liye use ki jati hai. React ko Facebook (ab Meta) ne develop kiya tha aur ise 2013 me release kiya gaya tha.

React ki help se hum **Single Page Applications (SPA)** aur **Dynamic Web Applications** ko easily develop kar sakte hain.

## Definition

**React JS** ek open-source JavaScript library hai jo reusable UI components ki madad se fast aur interactive user interfaces banane ke liye use hoti hai.

## Why React JS?

Traditional JavaScript me large applications ko manage karna difficult ho jata hai. React is problem ko solve karta hai by:

- Reusable Components
- Fast Rendering
- Easy State Management
- Better Code Organization
- Improved User Experience

## Key Features of React JS

### 1. Component-Based Architecture

React application chhote-chhote components me divide hoti hai.

Example:
- Header Component
- Navbar Component
- Product Component
- Footer Component

Har component ko alag se create aur reuse kiya ja sakta hai.

### 2. Virtual DOM

React actual DOM ko directly update nahi karta.

Ye pehle ek **Virtual DOM** create karta hai aur changes compare karke sirf required part ko update karta hai.

Benefits:
- Faster Rendering
- Better Performance
- Efficient Updates

### 3. Reusable Components

Ek component ko multiple places par use kiya ja sakta hai.

Example:

```jsx
<Product />
<Product />
<Product />
```

### 4. Declarative UI

React me hum UI ka desired state define karte hain aur React automatically UI update kar deta hai.

Example:

```jsx
function App() {
  const isLoggedIn = true;

  return (
    <div>
      {isLoggedIn ? <h1>Welcome User</h1> : <h1>Please Login</h1>}
    </div>
  );
}
```

### 5. One-Way Data Flow

Data Parent Component se Child Component me pass hota hai.

Benefits:
- Easy Debugging
- Predictable Data Flow
- Better Maintainability

## How React Works?

1. User action perform karta hai.
2. State ya Data change hota hai.
3. Virtual DOM update hota hai.
4. React old aur new Virtual DOM compare karta hai.
5. Sirf changed elements actual DOM me update hote hain.
6. UI re-render ho jata hai.

## Simple React Example

```jsx
function App() {
  return (
    <div>
      <h1>Hello React!</h1>
      <p>Welcome to React JS.</p>
    </div>
  );
}

export default App;
```

## Advantages of React JS

- Fast Performance
- Reusable Components
- Easy Learning Curve
- Large Community Support
- SEO Friendly (with frameworks like Next.js)
- Easy Maintenance
- Strong Ecosystem

## Real-World Applications Using React

- Facebook
- Instagram
- WhatsApp Web
- Netflix
- Airbnb
- Dropbox

## Summary

- React JS ek JavaScript Library hai.
- React ko Facebook (Meta) ne develop kiya hai.
- React UI banane ke liye use hota hai.
- React Component-Based Architecture follow karta hai.
- React Virtual DOM ki help se fast rendering provide karta hai.
- React modern web applications develop karne ke liye bahut popular hai.

# Difference Between Framework and Library

| Feature | Library | Framework |
|----------|----------|------------|
| Definition | Library pre-written code ka collection hoti hai jise hum apni requirement ke according use karte hain. | Framework ek complete structure provide karta hai jiske rules aur architecture ko follow karke application develop ki jati hai. |
| Control | Developer ke paas control hota hai ki kab aur kaise library ko use karna hai. | Framework control apne paas rakhta hai aur decide karta hai ki code kab execute hoga. |
| Flow of Control | Developer code ko control karta hai. | Framework application flow ko control karta hai. |
| Inversion of Control | Nahi hota. | Hota hai (Framework calls your code). |
| Flexibility | Zyada flexible hoti hai. | Kam flexible hoti hai kyunki predefined structure follow karna padta hai. |
| Learning Curve | Easy hoti hai. | Thodi difficult ho sakti hai. |
| Usage | Specific functionality provide karti hai. | Complete application development structure provide karta hai. |
| Example | React, Lodash, jQuery, Axios | Angular, Django, Laravel, Spring Boot |

# Features of React JS

- Component-Based Architecture
- Virtual DOM
- Reusable Components
- Declarative UI
- One-Way Data Binding
- Fast Rendering
- JSX (JavaScript XML)
- High Performance
- Easy State Management
- Efficient DOM Updates
- Unidirectional Data Flow
- Server-Side Rendering (SSR) Support
- Strong Community Support
- Easy Integration with Other Libraries
- Cross-Platform Development Support (React Native)
- SEO Friendly (with SSR Frameworks like Next.js)
- Code Reusability
- Simple Learning Curve
- Hot Reloading
- Large Ecosystem

# Create React Project

React project create karne ke liye sabse recommended command:

```bash
npm create vite@latest
```

Ya specific project name ke sath:

```bash
npm create vite@latest my-react-app
```

### Installation Steps

```bash
# Create Project
npm create vite@latest my-react-app

# Move into Project Folder
cd my-react-app

# Install Dependencies
npm install

# Start Development Server
npm run dev
```

## Alternative (Old Method)

```bash
npx create-react-app my-react-app
```

> Aaj kal React projects ke liye Vite zyada preferred hai kyunki ye faster aur lightweight hai.

# JSX (JavaScript XML)

## Introduction

JSX ka full form **JavaScript XML** hota hai.

JSX React ka ek syntax extension hai jo hume JavaScript ke andar HTML jaisa code likhne ki permission deta hai.

JSX ki help se UI ko create karna easy aur readable ho jata hai.

## Example

```jsx
const element = <h1>Hello React</h1>;
```

Yeh code HTML jaisa lag raha hai, lekin actually JSX hai.

## Why JSX?

Without JSX:

```jsx
const element = React.createElement(
    "h1",
    null,
    "Hello React"
);
```

With JSX:

```jsx
const element = <h1>Hello React</h1>;
```

JSX code zyada simple aur readable hota hai.

## Features of JSX

- HTML jaisa syntax provide karta hai.
- Code ko easy to read aur write banata hai.
- JavaScript expressions support karta hai.
- React Elements create karta hai.
- Better developer experience provide karta hai.

## JavaScript Expression in JSX

Curly Braces `{}` ke andar JavaScript expression likh sakte hain.

```jsx
function App() {
    const name = "Bittu";

    return <h1>Hello {name}</h1>;
}
```

### Output

```text
Hello Bittu
```

## JSX Rules

### 1. Single Parent Element

JSX me multiple elements ko ek parent element ke andar wrap karna hota hai.

✅ Correct

```jsx
return (
    <div>
        <h1>Title</h1>
        <p>Description</p>
    </div>
);
```

❌ Incorrect

```jsx
return (
    <h1>Title</h1>
    <p>Description</p>
);
```

### 2. Tags Must Be Closed

✅ Correct

```jsx
<img src="image.jpg" />
<input type="text" />
```

❌ Incorrect

```jsx
<img src="image.jpg">
<input type="text">
```

### 3. class ki Jagah className

React me `class` reserved keyword hai, isliye `className` use kiya jata hai.

✅ Correct

```jsx
<h1 className="title">Hello</h1>
```

❌ Incorrect

```jsx
<h1 class="title">Hello</h1>
```

### 4. JavaScript Code Curly Braces Me Likha Jata Hai

```jsx
const age = 21;

return <h1>Age: {age}</h1>;
```

## JSX Conversion

Browser JSX ko directly nahi samajhta.

Babel JSX ko normal JavaScript me convert karta hai.

```jsx
<h1>Hello</h1>
```

Convert hota hai:

```javascript
React.createElement("h1", null, "Hello");
```

## Summary

- JSX ka full form JavaScript XML hai.
- JSX React me HTML jaisa syntax provide karta hai.
- JSX code ko readable aur maintainable banata hai.
- Curly braces `{}` ke andar JavaScript expressions likh sakte hain.
- Browser JSX ko directly nahi samajhta, Babel ise JavaScript me convert karta hai.
- React applications me JSX sabse commonly use hone wala syntax hai.

# JSX Expressions

JSX Expression ka matlab hai **JavaScript Expression ko JSX ke andar use karna**.

React me Curly Braces `{}` ke andar JavaScript expressions likhe jate hain.

## Example

```jsx
function App() {
    const name = "Bittu";

    return <h1>Hello {name}</h1>;
}
```

### Output

```text
Hello Bittu
```

## Common Examples

```jsx
{10 + 20}

{name}

{name.toUpperCase()}

{isLogin ? "Welcome" : "Login"}

{greet()}
```

## Note

- JSX me Expressions use kar sakte hain.
- Expressions hamesha `{}` ke andar likhe jate hain.
- `if`, `for`, `while` jaise Statements directly JSX me use nahi kar sakte.

# Multiple Elements Render in React

React me ek component se multiple elements render karne ke liye hum mainly 4 tarike use kar sakte hain.

## 1. Array `[]`

```jsx
function App() {
    return [
        <h1 key="1">Heading</h1>,
        <p key="2">Paragraph</p>
    ];
}
```

> Array use karne par har element ke liye `key` dena zaruri hota hai.

---

## 2. Fragment Shorthand `<> </>`

```jsx
function App() {
    return (
        <>
            <h1>Heading</h1>
            <p>Paragraph</p>
        </>
    );
}
```

> Ye sabse common aur short syntax hai.

---

## 3. Div Wrapper `<div></div>`

```jsx
function App() {
    return (
        <div>
            <h1>Heading</h1>
            <p>Paragraph</p>
        </div>
    );
}
```

> Ye DOM me extra `<div>` create karta hai.

---

## 4. React.Fragment

```jsx
function App() {
    return (
        <React.Fragment>
            <h1>Heading</h1>
            <p>Paragraph</p>
        </React.Fragment>
    );
}
```

Ya Import karke:

```jsx
import React, { Fragment } from "react";

function App() {
    return (
        <Fragment>
            <h1>Heading</h1>
            <p>Paragraph</p>
        </Fragment>
    );
}
```

> Fragment DOM me extra element create nahi karta.

---

# React Components

## Introduction

React Component React application ka ek **reusable aur independent code block** hota hai jo UI ka ek part represent karta hai.

React application multiple components se milkar banti hai.

## Example

```jsx
function Header() {
    return <h1>Welcome to React</h1>;
}

export default Header;
```

Use:

```jsx
function App() {
    return <Header />;
}
```

## Types of Components

### 1. Functional Component

```jsx
function Welcome() {
    return <h1>Hello User</h1>;
}
```

### 2. Class Component

```jsx
import React, { Component } from "react";

class Welcome extends Component {
    render() {
        return <h1>Hello User</h1>;
    }
}
```

> Aaj kal mostly Functional Components use hote hain.

## Features

- Reusable
- Independent
- Easy to Maintain
- Easy to Test
- Code Reusability

## Naming Rule

Component ka naam hamesha **Capital Letter** se start hona chahiye.

✅ Correct

```jsx
function Header() {}
```

❌ Incorrect

```jsx
function header() {}
```

## Summary

- Component React ka building block hota hai.
- Ek component UI ka ek part represent karta hai.
- Components reusable hote hain.
- Functional aur Class Components do types hote hain.
- Modern React me Functional Components zyada use hote hain.

# Types of React Components

React Components mainly **2 types** ke hote hain:

1. Functional Component
2. Class Component

---

## 1. Functional Component

Ye ek normal JavaScript Function hota hai jo JSX return karta hai.

### Example

```jsx
function Welcome() {
    return <h1>Hello User</h1>;
}

export default Welcome;
```

### Use

```jsx
function App() {
    return <Welcome />;
}
```

---

## 2. Class Component

Ye ES6 Class hoti hai jo `React.Component` ko extend karti hai aur `render()` method use karti hai.

### Example

```jsx
import React, { Component } from "react";

class Welcome extends Component {
    render() {
        return <h1>Hello User</h1>;
    }
}

export default Welcome;
```

### Use

```jsx
function App() {
    return <Welcome />;
}
```

---

## Difference

| Functional Component | Class Component |
|----------|----------|
| JavaScript Function hota hai | ES6 Class hoti hai |
| Simple aur short syntax | Thoda lengthy syntax |
| Hooks support karta hai | Lifecycle Methods use karta hai |
| Modern React me zyada use hota hai | Ab kam use hota hai |

## Summary

- React me mainly 2 types ke Components hote hain.
- Functional Component → Function based.
- Class Component → Class based.
- Modern React me Functional Components sabse zyada use hote hain.

# Difference Between Functional Component and Function

| Feature | Functional Component | Normal Function |
|----------|----------|----------|
| Purpose | React UI render karne ke liye use hota hai | General JavaScript logic ke liye use hota hai |
| Return Value | JSX return karta hai | Koi bhi value return kar sakta hai |
| React Rendering | React ise render kar sakta hai | React ise directly render nahi kar sakta |
| Component Tag | `<Component />` se call hota hai | Normal function call `functionName()` se hota hai |
| Naming Convention | First letter Capital hona chahiye | Koi bhi valid name ho sakta hai |
| Hooks Use Kar Sakta Hai | ✅ Haan (`useState`, `useEffect`) | ❌ Nahi |
| JSX Support | ✅ Haan | ❌ Directly nahi |

## Functional Component Example

```jsx
function Welcome() {
    return <h1>Hello React</h1>;
}

function App() {
    return <Welcome />;
}
```

## Normal Function Example

```jsx
function greet() {
    return "Hello React";
}

function App() {
    return <h1>{greet()}</h1>;
}
```

## Short Note

- Functional Component UI banata hai.
- Normal Function logic perform karta hai.
- Functional Component ko `<Component />` se use karte hain.
- Normal Function ko `functionName()` se call karte hain.

# Exports in React

React me components, functions, variables etc. ko dusri files me use karne ke liye **export** kiya jata hai.

## 1. Default Export

Ek file me sirf **1 default export** ho sakta hai.

### Header.jsx

```jsx
function Header() {
    return <h1>Header Component</h1>;
}

export default Header;
```

### App.jsx

```jsx
import Header from "./Header";

function App() {
    return <Header />;
}
```

> Import karte waqt naam kuch bhi rakh sakte hain.

```jsx
import MyHeader from "./Header";
```

---

## 2. Named Export

Ek file me multiple named exports ho sakte hain.

### Utils.jsx

```jsx
export function Header() {
    return <h1>Header</h1>;
}

export function Footer() {
    return <h1>Footer</h1>;
}
```

### App.jsx

```jsx
import { Header, Footer } from "./Utils";

function App() {
    return (
        <>
            <Header />
            <Footer />
        </>
    );
}
```

> Named export import karte waqt same naam use karna padta hai.

---

## 3. Multiple Exports

Ek hi file se multiple components/functions export kar sakte hain.

### Components.jsx

```jsx

function Data() {
    return (
        <>
          <Header />
        </>
    );
}

export default Data;

export function Header() {
    return <h1>Header</h1>;
}

export function Navbar() {
    return <h1>Navbar</h1>;
}

export function Footer() {
    return <h1>Footer</h1>;
}

export cosnt UserKey = "Bittu@";
```

### App.jsx

```jsx
import Data, { Header, Navbar, Footer, UserKey } from "./Components";

function App() {
    return (
        <>
            <Header />
            <Navbar />
            <Footer />
            <UserKey/>
        </>
    );
}
```

---

## Summary

| Export Type | Syntax | Import Syntax |
|------------|---------|--------------|
| Default Export | `export default Header` | `import Header from "./Header"` |
| Named Export | `export { Header }` | `import { Header } from "./Header"` |
| Multiple Export | Multiple `export` | `import { Header, Footer } from "./Header"` |

## Important Points

- Ek file me sirf **1 Default Export** ho sakta hai.
- Ek file me **Multiple Named Exports** ho sakte hain.
- Named Export import karte waqt `{}` use karte hain.
- Default Export import karte waqt `{}` use nahi karte.

# ES6 Import and Export

## Named Export

### math.js

```javascript
export const name = "Bittu";

export function add(a, b) {
    return a + b;
}
```

### app.js

```javascript
import { name, add } from "./math";

console.log(name);
console.log(add(10, 20));
```

---

## Default Export

### math.js

```javascript
function add(a, b) {
    return a + b;
}

export default add;
```

### app.js

```javascript
import add from "./math";

console.log(add(10, 20));
```

---

## Default + Named Export Together

### math.js

```javascript
export const name = "Bittu";

export const age = 21;

function add(a, b) {
    return a + b;
}

export default add;
```

### app.js

```javascript
import add, { name, age } from "./math";

console.log(name);
console.log(age);
console.log(add(10, 20));
```

---

## Import Everything

### math.js

```javascript
export const name = "Bittu";

export const age = 21;

export function add(a, b) {
    return a + b;
}
```

### app.js

```javascript
import * as data from "./math";

console.log(data.name);
console.log(data.age);
console.log(data.add(10, 20));
```

---

## Summary

| Export Type | Export Syntax | Import Syntax |
|------------|--------------|--------------|
| Named Export | `export const name = "Bittu"` | `import { name } from "./math"` |
| Default Export | `export default add` | `import add from "./math"` |
| All Import | `export ...` | `import * as data from "./math"` |

### Important

- Named Export → `{}` lagte hain.
- Default Export → `{}` nahi lagte.
- Ek file me sirf **1 Default Export** ho sakta hai.
- Ek file me **multiple Named Exports** ho sakte hain.

# onClick Event in React

## 1. Function Call Without Parameter

```jsx
function App() {

    const showMessage = () => {
        alert("Hello React");
    };

    return (
        <button onClick={showMessage}>
            Click Me
        </button>
    );
}

export default App;
```

> Function ka reference pass kiya gaya hai.

---

## 2. Function Call With Parameter

```jsx
function App() {

    const showMessage = (name) => {
        alert(`Hello ${name}`);
    };

    return (
        <button onClick={() => showMessage("Bittu")}>
            Click Me
        </button>
    );
}

export default App;
```

> Parameter pass karne ke liye Arrow Function use karna padta hai.

---

## 3. Multiple Parameters

```jsx
function App() {

    const add = (a, b) => {
        alert(a + b);
    };

    return (
        <button onClick={() => add(10, 20)}>
            Add
        </button>
    );
}

export default App;
```

---

## ❌ Wrong Way

```jsx
<button onClick={showMessage("Bittu")}>
    Click Me
</button>
```

> Isme function component render hote hi execute ho jayega.

---

## ✅ Correct Way

```jsx
<button onClick={() => showMessage("Bittu")}>
    Click Me
</button>
```

## Summary

### Without Parameter

```jsx
onClick={showMessage}
```

### With Parameter

```jsx
onClick={() => showMessage("Bittu")}
```

### Multiple Parameters

```jsx
onClick={() => add(10, 20)}
```

# Template Literals in React

## Introduction

Template Literals JavaScript ka feature hai jisse hum strings ke andar variables aur expressions ko easily use kar sakte hain.

Template Literals me **backticks (` `)** ka use hota hai.

## Syntax

```javascript
`Text ${variable}`
```

---

## Example

```jsx
function App() {
    const name = "Bittu";

    return <h1>{`Hello ${name}`}</h1>;
}
```

### Output

```text
Hello Bittu
```

---

## Multiple Variables

```jsx
function App() {
    const firstName = "Bittu";
    const lastName = "Kumar";

    return (
        <h1>
            {`Welcome ${firstName} ${lastName}`}
        </h1>
    );
}
```

### Output

```text
Welcome Bittu Kumar
```

---

## Expression Inside Template Literal

```jsx
function App() {
    const a = 10;
    const b = 20;

    return <h1>{`Sum = ${a + b}`}</h1>;
}
```

### Output

```text
Sum = 30
```

---

## Without Template Literal

```jsx
const name = "Bittu";

return <h1>{"Hello " + name}</h1>;
```

---

## With Template Literal

```jsx
const name = "Bittu";

return <h1>{`Hello ${name}`}</h1>;
```

> Template Literals zyada readable aur easy hote hain.

## Summary

- Template Literals me backticks `` ` ` `` use hote hain.
- Variable ya expression ko `${}` ke andar likhte hain.
- String concatenation ko easy aur readable banate hain.

### Example

```jsx
{`Hello ${name}`}
```
# JSX Attributes

## Introduction

JSX Attributes ka use elements ko additional information ya properties dene ke liye kiya jata hai.

Ye HTML attributes ki tarah hi hote hain, lekin React me kuch attributes ke naam different hote hain.

## Syntax

```jsx
<tagName attributeName="value" />
```

## Example

```jsx
function App() {
    return (
        <img
            src="logo.png"
            alt="Logo"
        />
    );
}
```

---

## Common JSX Attributes

### className

```jsx
<h1 className="title">
    Hello React
</h1>
```

> React me `class` ki jagah `className` use hota hai.

---

### id

```jsx
<h1 id="heading">
    Welcome
</h1>
```

---

### src

```jsx
<img src="image.jpg" />
```

---

### alt

```jsx
<img
    src="image.jpg"
    alt="Profile"
/>
```

---

### href

```jsx
<a href="https://google.com">
    Google
</a>
```

---

### style

```jsx
<h1 style={{ color: "red" }}>
    Hello React
</h1>
```

> Style object ke form me diya jata hai.

---

## Dynamic Attribute

```jsx
function App() {
    const imageUrl = "logo.png";

    return <img src={imageUrl} />;
}
```

## Summary

- JSX Attributes element ko additional information dete hain.
- HTML attributes ki tarah use hote hain.
- `class` ki jagah `className` use hota hai.
- Dynamic values ke liye `{}` use karte hain.

### Example

```jsx
<h1 className="title">
    Hello React
</h1>
```

# Difference Between HTML Attributes and JSX Attributes

| Feature | HTML Attribute | JSX Attribute |
|----------|----------|----------|
| Used In | HTML | React JSX |
| class Attribute | `class` | `className` |
| for Attribute | `for` | `htmlFor` |
| Naming Convention | Mostly lowercase | CamelCase use hota hai |
| Event Handling | `onclick` | `onClick` |
| Style Attribute | String ke form me | JavaScript Object ke form me |
| JavaScript Values | Direct use nahi kar sakte | `{}` ke andar use kar sakte hain |

## Examples

### class vs className

#### HTML

```html
<h1 class="title">Hello</h1>
```

#### JSX

```jsx
<h1 className="title">Hello</h1>
```

---

### for vs htmlFor

#### HTML

```html
<label for="name">Name</label>
```

#### JSX

```jsx
<label htmlFor="name">Name</label>
```

---

### onclick vs onClick

#### HTML

```html
<button onclick="showMessage()">
    Click Me
</button>
```

#### JSX

```jsx
<button onClick={showMessage}>
    Click Me
</button>
```

---

### style

#### HTML

```html
<h1 style="color:red;">
    Hello
</h1>
```

#### JSX

```jsx
<h1 style={{ color: "red" }}>
    Hello
</h1>
```

---

### Dynamic Value

#### HTML

```html
<img src="image.jpg">
```

#### JSX

```jsx
<img src={imageUrl} />
```

## Summary

| HTML | JSX |
|--------|--------|
| `class` | `className` |
| `for` | `htmlFor` |
| `onclick` | `onClick` |
| Style String | Style Object |
| No JS Expressions | JS Expressions Allowed (`{}`) |

# CSS in React

React me CSS ko mainly **3 tariko se** use kiya jata hai:

1. External CSS
2. Internal CSS
3. Inline CSS

---

# 1. External CSS

CSS ko alag `.css` file me likha jata hai aur component me import kiya jata hai.

## App.css

```css
.title {
    color: red;
    font-size: 30px;
}
```

## App.jsx

```jsx
import "./App.css";

function App() {
    return (
        <h1 className="title">
            Hello React
        </h1>
    );
}

export default App;
```

---

# 2. Internal CSS

CSS ko component ke andar object bana kar use karte hain.

## App.jsx

```jsx
function App() {

    const headingStyle = {
        color: "blue",
        fontSize: "30px"
    };

    return (
        <h1 style={headingStyle}>
            Hello React
        </h1>
    );
}

export default App;
```

---

# 3. Inline CSS

CSS directly element ke `style` attribute me likhte hain.

## App.jsx

```jsx
function App() {
    return (
        <h1
            style={{
                color: "green",
                fontSize: "30px"
            }}
        >
            Hello React
        </h1>
    );
}

export default App;
```

---

# Summary

| CSS Type | Example |
|-----------|----------|
| External CSS | `import "./App.css"` |
| Internal CSS | `const styleObj = {}` |
| Inline CSS | `style={{ color: "red" }}` |

## Most Common

✅ External CSS

```jsx
import "./App.css";
```

## Internal CSS

```jsx
const styleObj = {
    color: "blue"
};
```

## Inline CSS

```jsx
style={{ color: "red" }}
```

