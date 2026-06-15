# React Js

### What is React?

React JS ek JavaScript library hai jo user interfaces (UI) banane ke liye use hoti hai. Yeh Facebook ne develop ki thi aur ab open-source hai. React ka main goal hai ki web applications ko efficient aur interactive banaya ja sake, especially jab applications me complex UI hota hai.

React ka kaam hota hai components ko banane mein. Ek component ek chhota part hota hai jo kisi UI ka hissa hota hai, jaise ek button, form, ya ek entire page. React ke components ko ek baar define karne ke baad aap unhe reuse kar sakte hain, jisse development kaafi fast aur efficient ho jata hai.

React ka ek aur important feature hai Virtual DOM. Virtual DOM ek in-memory representation hoti hai actual DOM ki. Jab bhi application mein koi change hota hai, React Virtual DOM ko update karta hai, phir actual DOM ko efficiently update karta hai. Is se performance improve hoti hai, kyunki React sirf unhi parts ko update karta hai jo change hue hote hain, pure page ko nahi.

React mein sab kuch components hote hain. Components ko aap soch sakte hain jaise ek chhota building block jo ek UI element ko represent karta hai. Har component apne aap mein independent hota hai aur apne state aur logic ko handle karta hai. Components do tarah ke hote hain:

##### Functional Components:

Yeh simple JavaScript functions hote hain jo props (data) ko accept karte hain aur ek UI render karte hain.

##### Class Components: 

Yeh React ke purane version mein use hote the. Inmein state aur lifecycle methods hote hain, jo functional components mein pehle available nahi the.

Ab React mein mostly functional components use kiye ja rahe hain, kyunki React ne Hooks introduce kiye hain jo functional components ko state aur side-effects handle karne mein madad karte hain.

## How React Works?

1. User action perform karta hai.
2. State ya Data change hota hai.
3. Virtual DOM update hota hai.
4. React old aur new Virtual DOM compare karta hai.
5. Sirf changed elements actual DOM me update hote hain.
6. UI re-render ho jata hai.

# React JS ke Advantages:-

#### Performance Optimization: 

Virtual DOM aur efficient rendering ki wajah se React applications high performance provide karte hain. Yeh browser ke real DOM se efficiently deal karta hai.

#### Reusable Components: 

Aap ek baar component bana kar use multiple places par use kar sakte hain. Yeh code reuse ko promote karta hai aur development ko speed up karta hai.

#### Large Community & Ecosystem: 
    
React ka ek bohot bada aur active community hai. Aapko React-related libraries, tools, aur resources easily mil jaate hain. Yeh aapko apne projects mein quickly implement karne mein madad karta hai.

#### Easy to Learn & Use: 
    
React ko seekhna relatively easy hai, especially agar aapko JavaScript ki basic understanding ho. JSX ki syntax intuitive hoti hai aur React ka ecosystem kaafi developer-friendly hai.

#### SEO Friendly: 
    
React ke server-side rendering (SSR) features ke saath, React applications SEO-friendly ban sakte hain. Yeh search engines ko aapke page ko better index karne mein madad karta hai.

#### Strong Tooling Support: 
    
React ke paas excellent tooling support hai, jaise React Developer Tools, create-react-app (for project setup), and various build tools like Webpack. Yeh aapke development process ko smooth aur efficient bana dete hain.

#### Wide Adoption in Industry: 
    
React ka use bohot saari large companies, jaise Facebook, Instagram, Airbnb, Netflix, and Uber ne kiya hai. Yeh demonstrate karta hai ki React ek reliable aur scalable solution hai for building modern web applications.

#### Declarative Syntax: 

React mein declarative approach ka use hota hai, jisme aap simply yeh batate hain ki UI kaise dikhna chahiye, aur React usko efficiently render kar deta hai. Yeh imperative programming ke comparison mein zyada user-friendly hota hai.

#### Fast Rendering: 

React ka diffing algorithm, jo Virtual DOM ka use karta hai, bahut fast hai. Iska matlab hai ki UI ko jaldi se render kiya jaata hai, jo end-user ke experience ko improve karta hai.

# React JS ke Features

#### Component-Based Architecture: 

React ka architecture component-based hai, matlab aap UI ko chhote, reusable components mein divide kar sakte hain. Har component apne aap mein independent hota hai aur apne state aur behavior ko manage karta hai.

Example:
- Header Component
- Navbar Component
- Product Component
- Footer Component

#### Virtual DOM: 
    
React virtual DOM ka use karta hai, jo ki real DOM ka lightweight version hota hai. Jab bhi koi change hota hai, React pehle virtual DOM mein update karta hai aur phir real DOM ko efficiently update karta hai. Isse performance boost milta hai.

Benefits:
- Faster Rendering
- Better Performance
- Efficient Updates

### Reusable Components

Ek component ko multiple places par use kiya ja sakta hai.

Example:

```jsx
<Product />
<Product />
<Product />
```

### One-Way Data Flow

Data Parent Component se Child Component me pass hota hai.

Benefits:
- Easy Debugging
- Predictable Data Flow
- Better Maintainability

#### Unidirectional Data Flow: 
    
React mein data ka flow one-way hota hai, yaani data parent se child components tak jata hai. Isse debugging asaan ho jaata hai aur code ko maintain karna easy ho jata hai.

#### JSX (JavaScript XML): 
    
React mein JSX ka use hota hai jo HTML aur JavaScript ko combine karta hai. Yeh ek syntax extension hai jisme aap JavaScript code ko directly HTML-like syntax mein likhte hain. Yeh development ko simple aur more readable banata hai.

#### Declarative UI: 
    
React declarative approach follow karta hai, jisme aap apni UI ko ek description ki tarah define karte hain. Iska matlab hai ki aap simply state aur data ko define karte hain aur React apne aap UI ko update kar deta hai.

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

#### React Hooks: 

React ne functional components mein hooks introduce kiye hain, jaise useState, useEffect, useContext, etc. Yeh state aur side effects ko manage karne ke liye use hota hai, aur functional components ko zyada powerful banata hai.

#### React Router: 
    
React Router ek package hai jo single-page applications (SPA) mein routing manage karne ke liye use hota hai. Yeh aapko dynamic routing aur URL handling ka facility deta hai.

#### React Router:

React Router ek library hai jo React applications me client-side routing ko enable karti hai. Yeh single-page applications me multiple views ko handle karta hai bina page ko reload kiye.

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

# JSX in React:

JSX (JavaScript XML) React mein ek syntax extension hai jo JavaScript ko HTML jaise structure mein likhne ki suvidha deta hai. Yeh React mein components ko define karne ke liye use hota hai.

JSX ka main purpose yeh hai ki hum JavaScript aur HTML ko ek hi file mein combine kar sakein, jisse code likhna aur samajhna dono asaan ho jata hai. JSX mein hum HTML tags jaise syntax ka istemal karte hain, lekin yeh JavaScript mein compile hota hai.


```js
import React from 'react';

function App() {
  return (
    <div>
      <h1>Hello, World!</h1>
    </div>
  );
}

export default App;

// or example

const element = <h1>Hello React</h1>;
```

## Why JSX?

Without JSX:

```jsx
const element = React.createElement(
    "h1",
    null,
    "Hello React"
);
```
## Features of JSX

- HTML jaisa syntax provide karta hai.
- Code ko easy to read aur write banata hai.
- JavaScript expressions support karta hai.
- React Elements create karta hai.
- Better developer experience provide karta hai.


##### JSX ke benefits:

Readability: HTML jaise syntax ki wajah se code ko samajhna aasaan hota hai.

Brevity: Shorter aur cleaner code likha ja sakta hai.

Component-based structure: React mein components ka use easily kiya ja sakta hai.

# How work JSX?

#### JSX Syntax: 

JSX ka syntax HTML ki tarah dikhta hai, lekin React usse JavaScript mein convert karta hai. JSX ek JavaScript expression hai, jise React.createElement() function ke through JavaScript mein convert kiya jata hai.


```python
const element = <h1>Hello, World!</h1>
```

Yeh code direct HTML jaise dikh raha hai, lekin jab browser ya React compiler isse process karta hai, toh yeh React.createElement() 
function mein convert ho jata hai:


```python
const element = React.createElement('h1', null, 'Hello, World!');
```

Iska matlab hai ki JSX ultimately React.createElement() ko call kar raha hai, jo ek React element create karta hai.

#### Compilation Process (Babel): 

React ke project mein, Babel ek JavaScript compiler hota hai jo JSX ko valid JavaScript mein convert karta hai. Jab aap React project mein JSX likhte hain, toh Babel is code ko is tarah se transform karta hai ki browser ya JavaScript engine use kar sake.


```python
const element = <h1>Welcome to React!</h1>;

// Babel isse JavaScript mein transform karega:

const element = React.createElement('h1', null, 'Welcome to React!');
```

#### React.createElement: 

React.createElement() ek function hai jo 3 arguments leta hai:

Type: HTML element (e.g., 'div', 'h1', etc.) ya React component.

Props: Element ke properties (e.g., className, style, etc.).

Children: Element ke andar jo content hoga, jo text ya nested elements ho sakte hain.


```python
const element = React.createElement('h1', { className: 'greeting' }, 'Hello, World!');

// Yeh h1 element banata hai, jisme ek class greeting aur text Hello, World! hota hai.
```

#### Rendering in DOM: 

Jab JSX ko JavaScript mein convert kiya jata hai aur React element ban jata hai, tab React ReactDOM.render() function ka use karke us element ko real DOM mein render karta hai. Yani, us element ko web page pe dikhata hai.


```python
ReactDOM.render(
  <h1>Hello, World!</h1>,
  document.getElementById('root')
);

```

#### Summary:
JSX HTML jaise dikhta hai, lekin ultimately JavaScript mein convert hota hai.

Babel JSX ko React.createElement() mein transform karta hai.

React phir is element ko real DOM mein render karta hai.

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


# What is component?

React me, component ek JavaScript function ya class hota hai jo UI (User Interface) ka ek part render karta hai. Components ki madad se hum apne UI ko chhote, reusability ke liye manageable hisso me divide kar sakte hain. Har component apna ek independent logic aur design rakhta hai aur jab data change hota hai, toh component apne aap ko re-render kar leta hai.

### Functional Components: 
Ye simple JavaScript functions hote hain jo props ko accept karte hain aur UI ko return karte hain. Yeh modern React development me zyada use hote hain, especially with hooks.


```python
function MyComponent(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

### Class Components: 
Yeh thoda purane tareeke se banaye jaate hain aur React ke lifecycle methods ko use karte hain. Ab React me functional components aur hooks ka use zyada ho raha hai.


```python
class MyComponent extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```
## Features

- Reusable
- Independent
- Easy to Maintain
- Easy to Test
- Code Reusability

> Aaj kal mostly Functional Components use hote hain.

## Naming Rule
Component ka naam hamesha **Capital Letter** se start hona chahiye.

✅ Correct
```jsx
function Header() {}
<!-- This is a component not function -->
```

❌ Incorrect
```jsx
function header() {}
<!-- This is a function, not component. -->
```
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

## Difference b/w components

| Functional Component | Class Component |
|----------|----------|
| JavaScript Function hota hai | ES6 Class hoti hai |
| Simple aur short syntax | Thoda lengthy syntax |
| Hooks support karta hai | Lifecycle Methods use karta hai |
| Modern React me zyada use hota hai | Ab kam use hota hai |

# Advantage of Components:

##### Reusability:
Components ko multiple places par reuse kiya ja sakta hai, jo development ko faster aur efficient banata hai. Agar aapne ek button ya form component banaya hai, to aap usse multiple screens ya pages par use kar sakte hain bina dobara likhe.

##### Modularity:
React mein UI ko chhote-chhote components mein divide kiya jata hai. Isse code clean aur maintainable rehta hai, aur agar koi problem ho to usse easily troubleshoot aur fix kiya ja sakta hai.

##### Separation of Concerns:
Components ko alag-alag tasks diye jate hain, jisse ek component sirf ek kaam karta hai (for example, ek form field ka validation ya ek button ka onClick event). Ye code ko simple aur understandable banata hai.

##### State Management:
React mein har component apna state manage kar sakta hai, jo UI ko update karne mein help karta hai jab user interact karta hai. Isse aapko complex state management ke liye external tools ki zaroorat nahi padti, jab tak aapka app chhota hai.

##### Easier Debugging:
Chhote components ko debug karna asaan hota hai, kyunki ek time par ek chhota piece of code manage ho raha hota hai. Isse errors ko pinpoint karna aur fix karna easy ho jata hai.

##### Performance Optimization:
React ka virtual DOM aur component lifecycle methods ka use karke performance ko optimize kiya ja sakta hai. Agar ek component ka state change hota hai, to sirf usi component ko re-render kiya jata hai, na ki poore app ko.

##### Testing:
Components ko independently test kiya ja sakta hai. Agar har component apne kaam mein self-contained hai, to unit testing aur integration testing kaafi asaan ho jati hai.


# Real DOM vs Virtual DOM:

#### Real DOM: 
Yeh actual DOM hai jo web browser mein hota hai. Jab bhi aapka page load hota hai, browser is DOM ko render karta hai. Har time jab page ke kisi part mein update hota hai, browser ko poore DOM ko re-render karna padta hai, jo performance ko slow bana sakta hai.
#### Virtual DOM: 
Yeh ek in-memory representation hai jo React use karta hai. Yeh real DOM ka lightweight copy hota hai, aur isme updates pehle kiye jate hain. React phir diffing algorithm use karke, old aur new virtual DOM ke beech changes ko calculate karta hai, aur sirf unhi parts ko real DOM mein update karta hai jo actually change hue hain.

React mein Virtual DOM ek concept hai jo ki real DOM (Document Object Model) ko optimize karne ke liye use hota hai. React app ke andar, jab bhi state ya UI update hota hai, React pehle ek virtual DOM mein changes karta hai aur phir actual DOM ko efficiently update karta hai.

#### React ka Virtual DOM kaise kaam karta hai: 
Jab React mein state ya props change hoti hai, to React sabse pehle virtual DOM mein changes karta hai. Yeh ek lightweight copy hota hai, aur changes ko efficient tareeqe se process karta hai. React phir yeh changes compare karta hai apne old virtual DOM se, aur diffing algorithm ke zariye, changes identify karta hai. Yeh algorithm, jo ki reconciliation algorithm kehlata hai, sirf un components ko real DOM mein update karta hai jo actually change hue hain. Is process se unnecessary rendering nahi hoti, aur app fast re-render hota hai.

## Virtual DOM ke kaam karne ka tareeqa

##### Initial Rendering: 
Jab React app pehli baar render hota hai, to React ek virtual DOM tree create karta hai jo ki real DOM ka lightweight copy hota hai.

##### Update Process: 
Jab state ya props mein koi change hota hai, React pehle virtual DOM mein changes karta hai. Iske baad, React comparison karta hai apne purane virtual DOM (previous state) aur naye virtual DOM (updated state) ke beech.

##### Diffing Algorithm: 
React ka diffing algorithm purane aur naye virtual DOM ke beech differences ko find karta hai. Sirf un parts ko update kiya jata hai jo change hue hain.

##### Efficient Update to Real DOM: 
Jab React ne differences identify kar liye, to wo sirf unhi parts ko real DOM mein update karta hai jo actually change hue hain, jisse performance improve hoti hai. Is process ko "reconciliation" kaha jata hai.

### Example:
Maan lijiye ki aap ek to-do list bana rahe hain. Jab aap ek new to-do item add karte hain:

Pehle, React virtual DOM mein naya to-do item add karta hai.

Fir, React virtual DOM mein changes ko old virtual DOM se compare karta hai.

Agar koi difference milta hai, to React sirf usi part ko real DOM mein update karta hai jo new to-do item ko show karega.

### Why Not Directly Modify the Real DOM?:
Directly real DOM ko modify karna inefficient ho sakta hai, kyunki browser ko har time poora page render karna padta hai. Agar app mein complex UI ho, aur state baar-baar change ho rahi ho, to baar-baar re-rendering performance ko bahut slow kar deti hai. Virtual DOM ki wajah se React sirf unhi parts ko update karta hai jo essential hai, aur isse rendering process fast ho jata hai.

### Virtual DOM ke fayde?

##### Performance Optimization:
Real DOM ke comparison mein, virtual DOM updates bahut fast hote hain kyunki React sirf necessary updates ko hi real DOM mein apply karta hai.

##### Efficiency: 
Puri UI ko dobara se render karne ki bajaye, React sirf un parts ko update karta hai jo actually change hue hain, isse unnecessary re-rendering se bachne mein madad milti hai.

##### Smooth User Experience: 
Yeh mechanism smooth aur responsive UI banata hai, kyunki updates fast aur efficient tareeqe se kiye jate hain.

##### Asynchronous Updates: 
React asynchronous updates perform karta hai, jo ki UI responsiveness ko improve karta hai.

# Reconciliation Process?

React mein reconciliation ek process hai jisme React apne virtual DOM aur actual DOM ko compare karke changes apply karta hai. Yeh process ensure karta hai ke UI efficiently update ho, sirf zaroori changes hi real DOM mein reflect ho.

### Steps of Reconciliation in React:
#### Virtual DOM: 
Jab React component ka state ya props change hoti hain, to React pehle uss component ka virtual DOM (ek in-memory representation) update karta hai.

#### Diffing Algorithm: 
React ka diffing algorithm virtual DOM ke purane version aur naye version ko compare karta hai. Yeh algorithm ye decide karta hai ke kaunse elements ko add, update ya remove karna hai.

#### Efficient Updates: 
Diffing algorithm ke result ke baad, React sirf un elements ko real DOM mein update karta hai jo actually change hue hote hain. Isse performance optimize hoti hai, kyunki poora DOM re-render nahi hota.

#### Example:
Agar ek component mein ek button hai jo click hone par text change karta hai, to jab button click hota hai:

React pehle virtual DOM mein changes apply karta hai.

Phir diffing algorithm ko use karte hue, React compare karta hai ke purani aur naye virtual DOM mein kya farq hai.

Sirf wo changes actual DOM mein reflect kiye jaate hain jo necessary hote hain.

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

# What is Props??
React me Props (jo ki "Properties" ka short form hai) ek bahut hi important concept hai. Agar aasan shabdon me kahein, to Props ka kaam ek Component se dusre Component me data bhejna hota hai.

## Code me kaise likhte hain?
### 1. Parent Component (Jo data bhej raha hai)
Yahan hum Car namak component ko call kar rahe hain aur usme brand aur color naam ke props bhej rahe hain.
```js
function App() {
  return (
    <div>
      {/* Humne brand aur color naam ke props bheje */}
      <Car brand="Ferrari" color="Red" />
      <Car brand="BMW" color="Black" />
    </div>
  );
}
```
### 2. Child Component (Jo data receive kar raha hai)
Yahan Car component ko ek object milta hai jise hum props kehte hain. Us object ke andar wo saari values hoti hain jo Parent ne bheji thin.
```js
function Car(props) {
  return (
    <h2 style={{ color: props.color }}>
      Hi, I am a {props.brand} car!
    </h2>
  );
}
```
- Read-Only (Immutable): Component ke andar aap props ki value ko badal nahi sakte. Agar Parent ne brand="BMW" bheja hai, to Child component use badal kar Audi nahi kar sakta. (Agar data badalna ho, to hum State ka use karte hain).

- Unidirectional Data Flow: Data hamesha upar se neeche jaata hai (Parent se Child ki taraf).

- Kuch bhi bhej sakte ho: Props me aap sirf text hi nahi, balki Numbers, Arrays, Objects, Boolean (true/false), aur yahan tak ki poore ke poore Functions bhi bhej sakte ho.


#  props and state?

### Props
(short for properties) ko hum parent component se child component tak data pass karne ke liye use karte hain. Ye read-only hote hain, yani ki child component apne props ko modify nahi kar sakta. Props se hum apne components ko dynamic bana sakte hain, kyunki hum alag-alag values pass kar sakte hain.

### State
ek component ka local data storage hota hai, jo sirf usi component ke liye hota hai. State ko hum update kar sakte hain, aur jab state change hoti hai, toh component dobara render hota hai. State ko hum user interaction ya kisi event ke basis par change karte hain. Ye mutable (update ho sakti) hoti hai, jo props ke comparison mein alag hai.

# State and Props Diff?

#### Definition:

Props: Parent se child component tak data pass karne ka tariqa hota hai.

State: Component ke apne data ko store karne aur manage karne ka tareeqa hota hai.

#### Mutability:

Props: Ye read-only hote hain, yani child component apne props ko change nahi kar sakta.

State: Ye mutable hote hain, yani component apni state ko change kar sakta hai.

#### Usage:

Props: Jab humein ek component se dusre component tak data pass karna ho, tab props ka use hota hai.

State: Component ke andar apne data ko track karne aur update karne ke liye state ka use hota hai.

#### Data Flow:

Props: Data ek direction mein flow karte hain — parent se child component tak.

State: State ka data ek hi component ke andar hota hai, aur uska flow change hota rehta hai jab state update hoti hai.

#### Change Trigger:

Props: Parent component jab props ko update karta hai, tab child component ko nayi props milti hain.

State: Jab state change hoti hai, toh component re-render hota hai, aur state ko update karna typically component ke apne actions (jaise user input) ke through hota hai.

#### Initial Value:

Props: Parent component se pass kiya gaya data initial value hota hai.

State: Component ka apna local data hota hai, jo initial value ke saath set kiya ja sakta hai (e.g., useState hook ke through).

#### Reusability:

Props: Same props ko multiple components mein reuse kiya ja sakta hai.

State: State component ke liye local hoti hai aur dusre components mein reuse nahi hoti.

| Feature       | Props                        | State                      |
| ------------- | ---------------------------- | -------------------------- |
| **Ownership** | Parent component se aata hai | Apne component ka hota hai |
| **Mutable?**  | Nahi (Immutable)             | Haan (Mutable)             |
| **Usage**     | Data share karna             | Data track/update karna    |
| **Control**   | Parent ke control mein       | Component ke control mein  |


# What is Hooks?

React me hooks ek special function hote hain jo functional components me state aur lifecycle features ko manage karne me madad karte hain. React hooks ko version 16.8 me introduce kiya gaya tha, jisse functional components me class components jaise features use kiye ja sakte hain.

# higher-order component

Higher-Order Component (HOC) React mein ek design pattern hai jo ek function hota hai, jo kisi component ko as an argument accept karta hai aur ek naya component return karta hai. Iska main purpose ek existing component ko enhance karna hota hai bina uske original code ko change kiye. HOC ka use common logic ko share karne ke liye kiya jata hai, jaise authentication check, data fetching, etc.

HOC ek function hai jo ek component ko accept karta hai aur usse wrapped component return karta hai.


```python
const withSomething = (WrappedComponent) => {
  return class extends React.Component {
    render() {
      // Common functionality ya logic add kar sakte hain yaha
      return <WrappedComponent {...this.props} />;
    }
  };
};
```

#### Key points:
HOC kabhi bhi props ko modify nahi karta, bas component ko enhance karta hai.

HOC ko components ko reusability aur shared functionality ke liye use kiya jata hai.

HOC React ke built-in features ka part nahi hai, ye ek design pattern hai.

# Pure Components in React

React me Pure Components ek aise components hote hain jo sirf tab re-render hote hain jab unki props ya state me koi changes aaye. React me PureComponent ek built-in class hoti hai jo shouldComponentUpdate method ko optimize karti hai. Iska fayda yeh hai ki unnecessary re-renders avoid hote hain, jo application ki performance ko improve karte hain.

### PureComponent ka kaam:
PureComponent automatically shallow comparison karta hai props aur state ka. Matlab, agar props ya state me koi deep change nahi hota, to component ko re-render nahi kiya jata.

Agar aap regular component (jo class se bana ho) use karte hain, to aapko shouldComponentUpdate method manually likhna padta hai.

PureComponent use karte waqt aapko shouldComponentUpdate likhne ki zarurat nahi padti, kyunki React khud hi shallow comparison karta hai.

#### Advantages:
Performance improve hoti hai kyunki unnecessary renders avoid hote hain.

Code ko simple aur efficient banaya jata hai.

#### Important Note:
PureComponent shallow comparison karta hai, isliye agar props ya state me koi complex object (e.g., arrays ya objects) hai, to agar unme internal changes hote hain (jaise array ke elements ya object ke properties), tab bhi component ko re-render kiya jayega. Aise cases me React.memo ya deep comparison ka use karna padta hai

# Software Development Life Cycle

Software Development Life Cycle (SDLC) ek process hai jo software applications ko design, develop, test, aur maintain karne ke liye follow kiya jata hai. Is process ka maqsad software ke high-quality, reliable, aur efficient versions ko time pe deliver karna hai. SDLC mein kai phases hote hain, jinhein sequentially ya iterative tarike se follow kiya jata hai.

### Planning
Goal: Project ki scope aur requirements ko samajhna.

Is phase mein, software development team aur stakeholders (clients, users, etc.) milke project ke goals define karte hain. Yeh phase software ke functionalities aur features ko clearly document karta hai.

Output: Requirement Specification Document (SRS - Software Requirement Specification), jo batata hai ki software ko kis tarah se develop karna hai aur kya expectations hain

### Requirements:
In this stage, all the requirements for the target software are specified. These requirements get approval from customers, market analysts, and stakeholders. 

This is fulfilled by utilizing SRS (Software Requirement Specification). This is a sort of document that specifies all those things that need to be defined and created during the entire project cycle. 

### Architecture / System Design
Goal: Architecture aur design ko plan karna.

Is phase mein, software ka architecture design kiya jata hai. Yahan par technical specifications, database design, user interfaces (UI), aur system ke components ke structure ko define kiya jata hai.

Types of Design:
##### High-level Design (HLD): System ke overall structure ko define karta hai, jaise modules ka interaction aur data flow.

##### Low-level Design (LLD): Detailed design hota hai, jisme individual components ki design aur code logic define hota hai.
Output: Design Document, jo development ke liye blueprint ka kaam karta hai.

### Implementation (Coding/Development)
Goal: Software code likhna.

Is phase mein developers software ko actual code ke roop mein implement karte hain. Development team system design ke hisaab se programming languages, frameworks, aur tools ka use karte hue software banate hain.

Developers ko ensure karna hota hai ki code sahi tarike se likha jaye aur efficient ho.

Output: Source code, jo ki system design aur specifications ke mutabiq hota hai.

### Testing
Goal: Software ko bugs aur issues ke liye test karna.

Testing phase mein, software ko multiple test cases ke through check kiya jata hai. Yeh phase ensure karta hai ke software requirements ke according kaam kar raha hai aur koi bugs ya errors na hon.

Types of Testing:

Unit Testing: Individual components ya modules ka testing.

Integration Testing: Multiple modules ko integrate karke unka testing.

System Testing: Puri system ko test karna.

User Acceptance Testing (UAT): End-users ke dwara testing, taake confirm ho sake ki software unki requirements ko fulfill kar raha hai.

Output: Test Reports aur Bug Fixes.

### Deployment
Goal: Software ko production environment mein release karna.

Jab software test ho jata hai, tab usse end-users ke liye deploy kiya jata hai. Is phase mein, software ko actual environment mein install aur configure kiya jata hai.

Deployment kai stages mein ho sakta hai: first, beta version release hota hai, fir full-scale release.

Output: Deployed Software in Production.

### Maintenance
Goal: Software ki performance aur functionality ko monitor karna aur improve karna.

Deployment ke baad, software ko continuously maintain kiya jata hai. Yeh phase software ko update karne, bugs ko fix karne, aur user feedback ke basis par improvements karne ka kaam karta hai.

Types of Maintenance:

Corrective Maintenance: Bugs ko fix karna jo production mein aaye hain.

Adaptive Maintenance: Software ko updates ya changes ke liye adapt karna, jaise new features add karna ya environment changes ke liye.

Perfective Maintenance: Existing features ko enhance karna.

Preventive Maintenance: Future issues ko prevent karne ke liye changes aur improvements.

# Models of SDLC

## Waterfall Model:-

Waterfall Model SDLC (Software Development Life Cycle) ka ek traditional approach hai, jisme development process sequential hoti hai. Is model mein har phase ek ke baad ek complete hota hai, aur jab ek phase complete ho jata hai, tab hi agla phase start hota hai. Iska naam "Waterfall" isliye rakha gaya hai kyunki ek phase ka output doosre phase ke liye input ban jata hai, jaise paani ek waterfall mein neeche girta hai.

Waterfall Model ek linear aur sequential approach hai jisme ek phase complete hone ke baad hi agla phase start hota hai. Yeh ek rigid process hai, aur har phase ka apna ek defined output hota hai, jo agle phase ka input ban jaata hai.

## Waterfall Model ke phases ko thoda aur detail mein samajhte hain:

### Requirement Analysis:
Is phase mein client se milke unki requirements ko samjha jaata hai.

Sabhi functional aur non-functional requirements ko document kiya jaata hai.

Yeh phase sabse pehle hota hai aur isme system ki overall functionality ka overview liya jaata hai.

Requirement clear hone ke baad, kisi bhi changes ki planning future mein mushkil ho sakti hai.

### System Design:
Is phase mein, architecture aur design banaya jaata hai jo requirements ke basis par hota hai.

Do tarah ka design hota hai:

High-Level Design (HLD): Yeh system ke architecture aur components ko define karta hai.

Low-Level Design (LLD): Yeh components ke detailed design ko define karta hai, jaise ki databases, user interfaces, etc.

Design phase ke output ko developers aur testers use karte hain aage ke phases ke liye.

### Implementation (Coding):
Jab design final ho jaata hai, tab actual coding ka kaam start hota hai.

Developers is phase mein code likhte hain jo design document ke according hota hai.

Yeh phase typically longest phase hota hai.

Code likhne ke baad, modules ko integrate kiya jaata hai aur testing ki planning hoti hai.

### Integration and Testing (Verification):
Jab coding complete hoti hai, tab system ko integrate karke testing start hoti hai.

Testing mein system ki functionality check ki jaati hai ki wo requirements ke according kaam kar raha hai ya nahi.

Agar koi bugs ya errors milte hain, toh unhe fix kiya jaata hai. Agar system expected behavior ke according kaam nahi kar raha hota, toh developers ko phir se code mein changes karne padte hain.

Yeh phase bugs ko identify karne aur fix karne ka kaam karta hai.

### Deployment (Installation):
Jab testing complete ho jaati hai aur system bug-free ho jaata hai, tab system ko deployment ke liye ready kiya jaata hai.

System ko production environment mein install kiya jaata hai taaki end-users isse use kar sakein.

Deployment ke baad, system ko users ko deliver kar diya jaata hai.

### Maintenance:
Jab system live ho jaata hai aur users use karna shuru karte hain, tab maintenance phase start hota hai.

Is phase mein system ko regularly update kiya jaata hai, bugs fix kiye jaate hain, aur enhancements kiye jaate hain.

Maintenance ke dauran system ko optimize bhi kiya jaa sakta hai aur naye features bhi add kiye ja sakte hain.

### Features:-
#### Sequential Process: 
Har phase ka ek clear output hota hai, jo agle phase ko input banata hai.

#### Documentation: 
Har phase ke completion ke baad extensive documentation banayi jaati hai, jo project ke progress ko track karne mein madad karti hai.

#### Clear Milestones: 
Har phase ka apna ek defined milestone hota hai, jisme next phase ke liye input ready hota hai.

#### Rigid Structure: 
Waterfall model ka structure kaafi rigid hota hai. Agar aapko development ke dauran requirements mein koi change karna ho, toh wo kaafi mushkil ho sakta hai, kyunki ek phase complete hone ke baad aapko pehle ke phases mein changes karne padte hain.

### Advantages:-
Simple aur Easy to Understand

Clear and Structured Phases

Good Documentation

Individual Processing

### Disadvantages:-

Inflexible

Late Testing

High Risk

No Overlapping of Phases

Lengthy Development Cycle

#### Waterfall Model ka use kab hota hai?
Waterfall model un projects mein zyada use hota hai jahan requirements clear ho, scope stable ho, aur project ka complexity low ho. Example ke liye, small or simple projects jaise ek fixed software tool ya application jo clearly defined requirements ke saath banani hoti hai, wahan waterfall approach kaafi useful hoti hai.

# Agile Model

Agile model, Software Development Life Cycle (SDLC) ka ek popular approach hai jo software development process ko iterative aur incremental banaata hai. Iska goal hai flexibility aur customer ke feedback ke basis par software ko continuously improve karna. Is model mein, development process ko chhote-chhote cycles ya "sprints" mein divide kiya jaata hai.

### Agile Frameworks: 
Jaisa ki maine pehle bataya, Agile ek umbrella term hai, aur iske andar kayi different frameworks aate hain, jinme se kuch popular hain:

#### Scrum: 
Scrum ek iterative framework hai jisme development process ko chhote sprints mein divide kiya jaata hai. Har sprint ke baad product increment deliver hota hai. Scrum mein Product Backlog, Sprint Backlog, Daily Standups, Sprint Planning, etc., ke specific ceremonies aur roles defined hote hain.

#### Kanban: 
Kanban ek visual framework hai jisme tasks ko visual boards pe track kiya jaata hai. Har task ko ek specific column mein rakha jaata hai, jaise "To Do", "In Progress", "Completed". Iska main goal workflow ko optimize karna aur bottlenecks ko identify karna hota hai.

#### Extreme Programming (XP): 
XP ka focus hai software development mein quality ko improve karna, jaise ki continuous integration, pair programming (do developers ek saath kaam karte hain), automated testing, aur frequent releases.

# UseState Hook's

useState hook React me ek built-in hook hai jo functional components me state ko manage karne ke liye use hota hai. React me, jab hum functional component bana rahe hote hain, to hum directly this.state ya this.setState jaise class components wale state management methods ko use nahi kar sakte. useState hook ka use karke hum apne functional components me state create kar sakte hain aur usko update kar sakte hain.

##### const [state, setState] = useState(initialState);

state: Ye variable hai jisme hum apni state value store karte hain.

setState: Ye ek function hai jo state ko update karne ke liye use hota hai.

initialState: Ye wo initial value hai jo hum apni state ko dena chahte hain.

#### React Functional Component Mein State
useState ko use karne se pehle, React ke functional components mein state ko manage karna possible nahi tha. Class components me state ko manage karne ke liye hum this.state aur this.setState ka use karte the, lekin functional components me aisa koi mechanism nahi tha. useState hook ko introduce karke React ne is problem ka solution diya.

#### State ko Track Karna
Jab aap useState hook ka use karte hain, React us state ko track karta hai. Agar aap state ko update karte hain to React ko pata chal jata hai aur wo apne component ko re-render karta hai. Har time jab state update hoti hai, component ko nayi value ke saath dobara render kiya jata hai.


```python
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  const handleIncrease = () => {
    setCount(count + 1);
    console.log(count);  // Ye purani value print karega, state update ke baad nahi.
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={handleIncrease}>Increase</button>
    </div>
  );
}

export default Counter;
```

#### Multiple States in One Component


```python
import React, { useState } from 'react';

function UserInfo() {
  const [name, setName] = useState('');
  const [age, setAge] = useState(0);

  const handleNameChange = (e) => {
    setName(e.target.value);
  };

  const handleAgeChange = (e) => {
    setAge(e.target.value);
  };

  return (
    <div>
      <input type="text" value={name} onChange={handleNameChange} placeholder="Enter name" />
      <input type="number" value={age} onChange={handleAgeChange} placeholder="Enter age" />
      <p>Name: {name}</p>
      <p>Age: {age}</p>
    </div>
  );
}

export default UserInfo;
```

#### State ko Object ke Form Mein Store Karna


```python
const [user, setUser] = useState({
  name: 'John',
  age: 30
});

// Update state
const updateUser = () => {
  setUser(prevUser => ({ ...prevUser, age: 31 }));
};
```

# UseEffect Hook's

React mein useEffect hook ek built-in hook hai jo functional components mein side effects handle karne ke liye use hota hai. Side effects se matlab hai wo operations jo React component render hone ke baad perform kiye jaate hain, jaise data fetching, subscriptions, DOM manipulations, ya timers.

useEffect hook ko React mein side effects ko manage karne ke liye use kiya jata hai, jise hum lifecycle methods (jaise componentDidMount, componentDidUpdate, componentWillUnmount) ko functional components mein replace karte hain.


```python
useEffect(() => {
  // side effect logic yahan likhenge
}, [dependencies]);
```

Pehla argument: A function jo side effect ko perform karega.Yeh function wo code hota hai jo hum chahte hain ke effect execute ho, jaise ki data fetch karna, DOM manipulation, event listeners set karna, etc.

Dusra argument: A dependency array, jismein aap specify karte ho ke kaunse values ya state variables ke change hone par side effect run hoga. Agar ye array khali ho, toh side effect sirf component ke first render par chalega. Agar koi dependencies specified hain, toh side effect un dependencies ke change hone par execute hoga.


```python
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Side effect: count update hone par console log
  useEffect(() => {
    console.log('Count has been updated:', count);
  }, [count]); // Dependency array: count ke change hone par effect chalega

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

* useEffect ko functional components mein lifecycle methods ko replace karne ke liye use kiya jata hai.
* Agar aap dependency array mein empty array ([]) rakhte hain, toh effect sirf component ke first render par chalega.
* Agar aap dependencies specify karte hain, toh effect un dependencies ke change hone par chalega.
* Cleanup functions ko useEffect ke andar return statement se handle kiya ja sakta hai.
* useEffect React mein lifecycle methods ka equivalent hai. Agar aapko componentDidMount, componentDidUpdate, ya componentWillUnmount ki tarah behavior chahiye ho, toh useEffect ko properly use kar sakte hain.

##### useEffect ke kuch common use cases:-
* Data Fetching
* Event Listeners
* Updating the Document Title
* Cleanup Functions

# UseMemo Hook's

useMemo React hook ka use component ke re-render ke dauran costly calculations ya functions ko optimize karne ke liye hota hai. Iska main purpose performance ko improve karna hai, taaki unnecessary re-renders ya recalculations na ho.

Jab bhi kisi component ka state ya props change hota hai, to by default wo component re-render hota hai. Agar kisi specific calculation ko baar-baar dobara run karna ho, jo costly ho, to useMemo ka use karte hain taaki wo calculation sirf tab hi execute ho jab dependencies change hoti hain, na ki har re-render par.

##### useMemo ka kaam kis tarah se hota hai?
useMemo ka primary purpose hota hai costly computations ko optimize karna. Agar aapke component me koi aisi calculation ho jo har render pe execute hoti ho, to us calculation ko useMemo ke andar wrap karke aap usse sirf tab run karwa sakte hain jab required dependencies change ho. Isse unnecessary calculations se bach jaate hain aur performance improve hoti hai.

##### useMemo ka behaviour:
Memoization ka matlab hai kisi value ko store karke rakhna, taki usse dobara calculate na karna pade jab tak us value ko forcefully re-compute karne ki zarurat na ho.

Jab aap useMemo ko call karte hain, React dependency array ko monitor karta hai. Agar dependency array ke items (jaise count, text, etc.) me koi change hota hai, tabhi React useMemo ke andar di gayi function ko dobara execute karega. Agar dependencies me koi change nahi aata to React us value ko reuse karega jo pehle compute ki gayi thi.

#### useMemo ko kab use karein?
Heavy Calculations: Agar aapka component me koi calculation ya function execution bohot heavy ho (e.g., sorting large arrays, filtering large datasets), to useMemo se us calculation ko optimize kar sakte hain.

Re-render Optimization: Agar aapke component me kisi object ya array ka reference repeatedly change ho raha ho, to useMemo se aap us object ko stable rakh sakte hain. Iska matlab hai, object ya array ka reference wahi rahega jab tak uska actual content change na ho. Yeh React ke re-rendering ko optimize karta hai.

#### useMemo ka use kahan karein:
Jab aapko kisi calculation ko memoize karna ho jo costly ho (e.g., loops, data processing).

Jab aapko kisi object ya array ko memoize karna ho taaki unnecessary re-renders na ho.


```python
#Syntax

const sortedData = useMemo(() => {
 return expensiveSort(data);
}, [data]);
```

#### useMemo vs useCallback:
Agar aapko lagta hai ki aapko function ko memoize karna hai, to useMemo ka use kar sakte hain. Agar aapko specifically function ka reference memoize karna ho, to useCallback use karna better hota hai.

* useMemo ko use karte hain jab aap kisi value ko memoize karna chahte hain.

* useCallback ko use karte hain jab aapko ek function ko memoize karna ho.


```python
// useCallback example
const memoizedCallback = useCallback(() => {
  console.log("This is memoized");
}, []);
// Memoized function that doesn't change unless dependencies change.
```

#### Jab useMemo ka use avoid karein:
Agar aapko lagta hai ki optimization ke liye useMemo ko zaroori nahi hai, to isse avoid karein. React already kaafi optimizations karta hai.

Agar aapke calculations ka impact bahut chhota hai (e.g., quick calculations ya simple rendering), to useMemo unnecessary ho sakta hai, aur ye extra complexity la sakta hai jo aapke code ko hard to maintain bana dega.

#### Summary:
useMemo ek powerful hook hai jo costly computations ko avoid karta hai aur performance ko optimize karta hai by memoizing values. Iska use aap tab karein jab aapko heavy calculations ya frequent re-renders ko optimize karna ho. Agar aap isse unnecessarily use karenge, to React ka internal optimization mechanism slow ho sakta hai.

# UseRef Hook's

useRef React ka ek hook hai jo ek mutable reference object ko create karta hai jo component re-renders ke dauran preserve hota hai. Iska main use case DOM elements ko reference dena aur unki values ko track karna hai without causing re-renders.


```python
#Syntax
import { useRef } from 'react';

function MyComponent() {
 const latestScore = useRef(0);
 
 // Updating the latestScore
 latestScore.current = 100;
 
 // Accessing the latestScre
 console.log('Latest Score:', latestScore.current);
 
 return (
 <div>
 {/* Your component JSX */}
 </div>
 );
}
```

#### useRef ka use:
DOM elements ko reference dena: Agar aapko kisi DOM element ko directly access karna ho (e.g., ek input field), to useRef ka use kiya jaata hai.

Persisting values across renders: useRef ko aap kisi value ko store karne ke liye bhi use kar sakte hain jo render ke dauran change hoti hai, lekin re-render nahi chahte.

##### DOM Reference ke liye:
Agar aapko kisi DOM element ko directly access karna hai, jaise ek input box ya button, to useRef bahut useful hota hai. React me ref ek aisa object hai jo DOM element ko point karta hai. useRef hook usi ref ko create karne ka kaam karta hai.


```python
import React, { useRef } from 'react';

function MyComponent() {
  const inputRef = useRef();

  const focusInput = () => {
    // Directly accessing the input element using ref
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={focusInput}>Focus the input</button>
    </div>
  );
}
```

Yahan, inputRef.current se hum directly input element ko access kar rahe hain, aur button click par usse focus kar rahe hain. Yeh inputRef.current me direct reference hai input field ka.

##### State Preservation Without Re-rendering:
Jab aapko kisi value ko track karna ho jo baar-baar update ho, lekin aap nahi chahte ki component dobara render ho, tab useRef useful hota hai. Jaise ki agar aapko kisi value ko track karna ho jo ek event ya timer ke through change ho rahi ho, to aap useRef ka use kar sakte hain.


```python
import React, { useState, useEffect, useRef } from 'react';

function TimerComponent() {
  const [time, setTime] = useState(0);
  const previousTimeRef = useRef();

  useEffect(() => {
    previousTimeRef.current = time;
  }, [time]);

  return (
    <div>
      <p>Current Time: {time}</p>
      <p>Previous Time: {previousTimeRef.current}</p>
      <button onClick={() => setTime(time + 1)}>Increment Time</button>
    </div>
  );
}
```

Yahan, previousTimeRef useRef se banaya gaya hai aur usme previous time value store ki ja rahi hai. Jab bhi time update hota hai, previousTimeRef.current ko update kiya jata hai, lekin component ko dobara render nahi karna padta.

##### Key Points:

* Initial Value: useRef ko ek initial value di ja sakti hai (optional), jo initial render ke waqt reference object me stored hoti hai.

* Preserving State: useRef se jo reference object milta hai, uska current property value ko store karta hai. Agar current ko update karte ho, to component re-render nahi hota.

* No Re-renders: Agar ref object ki current property ko update kiya jata hai, to component re-render nahi hota.

##### Summary:
* useRef ek hook hai jo ek mutable reference object create karta hai.
* DOM elements ko reference dena aur state ko track karna without re-rendering ke liye use hota hai.
* useRef ko event listeners ya animations me bhi use kiya ja sakta hai.
* Ye state ki tarah kaam karta hai, lekin ref me update hone par component re-render nahi hota.
* State ko track kar sakte ho bina component ko re-render kiye.

useRef() reactJs interview mai puch le toh ab easily samjha dena interviewer ko

useRef ek React hook hai jo humein allows karta hai ki hum kisi component mein ek persistent value ko store kar sake, jo render hone ke bawajood change nahi hota.

Real-Life Example: Imagine a cricket match! Jab hum scoreboard dekhte hain, waha current score dikhta hai, lekin last wicket jo gira tha, woh bhi important hota hai. Yahi useRef humein karta hai! Woh store karta hai last wicket ka information jab tak humein zarurat ho.

Machine-Level Impact: Machine level mein, useRef hamare components ko ek aisa "sticky note" provide karta hai jisme hum extra information rakhte hain, jo render hote samay change nahi hoti. Isse performance bhi improve hoti hai!

### useRef vs useState:
useState: Jab aap state update karte ho, to component re-render hota hai. State ko UI se link kiya ja sakta hai.

useRef: Jab aap ref ko update karte ho, to component re-render nahi hota. ref mostly DOM se related hota hai ya aise values ko store karta hai jo UI se directly related nahi hoti.


```python
import React, { useRef } from 'react';

function MyComponent() {
  const inputRef = useRef();

  const focusInput = () => {
    // Ref se input ko focus karo
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={focusInput}>Focus the input</button>
    </div>
  );
}
```

`Explanation: inputRef ke through aap direct input field ko access karte ho aur button click karte hi input ko focus karte ho. Yeh inputRef.current ke through hota hai.`

# What is conditional rendering in React?


Conditional rendering React mein ek technique hai jisme component user ke action, state ya kisi condition ke base par alag-alag output dikhata hai. Matlab, React dynamically decide karta hai ki kaunsa element ya component render karna hai.

### If-else condition ka use:


```python
function Greeting(props) {
  if (props.isLoggedIn) {
    return <h1>Welcome back!</h1>;
  } else {
    return <h1>Please sign in.</h1>;
  }
}
```

### Ternary operator (Short form of if-else):



```python
function Greeting(props) {
  return (
    <h1>{props.isLoggedIn ? "Welcome back!" : "Please sign in."}</h1>
  );
}
```

### Logical AND (&&) operator:


```python
function Notification(props) {
  return (
    <div>
      {props.hasNotification && <p>You have new messages!</p>}
    </div>
  );
}
```

#### Real-life Example:

Agar ek login system banana ho jisme button ka text "Login" ya "Logout" user ke status ke base par change ho


```python
function LoginButton(props) {
  return <button onClick={props.onClick}>Login</button>;
}

function LogoutButton(props) {
  return <button onClick={props.onClick}>Logout</button>;
}

function UserControl(props) {
  const [isLoggedIn, setIsLoggedIn] = React.useState(false);

  const handleLogin = () => setIsLoggedIn(true);
  const handleLogout = () => setIsLoggedIn(false);

  return (
    <div>
      {isLoggedIn ? (
        <LogoutButton onClick={handleLogout} />
      ) : (
        <LoginButton onClick={handleLogin} />
      )}
    </div>
  );
}
```

# What are the differences between React and Angular/Vue?


| **Aspect**            | **React**                               | **Angular**                                |
| --------------------- | --------------------------------------- | ------------------------------------------ |
| **Type**              | Library for building UI components      | Full-fledged MVC framework                 |
| **Language**          | JavaScript + JSX                        | TypeScript                                 |
| **Architecture**      | Component-based                         | Component-based, MVVM                      |
| **DOM Handling**      | Virtual DOM                             | Real DOM with Zone.js for change detection |
| **Data Binding**      | One-way (Unidirectional)                | Two-way and One-way                        |
| **State Management**  | Redux, Context API, MobX (Third-party)  | In-built (RxJS + Services)                 |
| **Routing**           | React Router (Third-party)              | In-built (Angular Router)                  |
| **Performance**       | High (Efficient reconciliation)         | Medium (Change detection overhead)         |
| **Learning Curve**    | Moderate (JSX + State Management)       | Steep (TypeScript, Dependency Injection)   |
| **Size**              | Lightweight (\~42KB)                    | Heavy (\~500KB)                            |
| **Ecosystem**         | Flexible, relies on third-party tools   | Complete solution, all in-built            |
| **Scalability**       | Excellent for large apps (customizable) | Ideal for enterprise-level apps            |
| **Community Support** | Large (Backed by Meta/Facebook)         | Large (Backed by Google)                   |
| **Use Cases**         | SPAs, Dashboards, Real-time Apps        | Enterprise-scale apps, Complex apps        |
| **Examples**          | Facebook, Instagram, Airbnb             | Google products, Upwork                    |


#### React Highlights:

Virtual DOM: Ensures faster UI updates by reconciling changes.

Unidirectional Data Flow: Makes it predictable and debuggable.

Flexibility: Requires third-party tools for routing, state management, etc.

JSX Syntax: Combines HTML and JavaScript, making it powerful yet a bit tricky to learn.

#### Angular Highlights:

TypeScript: Provides strong typing and better tooling.

Two-way Binding: Simplifies UI updates with real-time synchronization.

In-built Features: Everything is provided out-of-the-box, including HTTP, forms, routing, etc.

Change Detection: Uses Zone.js for monitoring asynchronous tasks, which can affect performance in large apps.


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
# tenury operated
Kyunki React ke JSX ke andar hum direct if-else nahi likh sakte, isliye Ternary Operator React me conditional rendering (yaani condition ke hisab se kuch dikhane ya chhupane) ka sabse pasandida tareeka hai.

`$$\text{Condition} \ ? \ \text{Agar True ho to yeh chalao} \ : \ \text{Agar False ho to yeh chalao}$$`

### React me iske Use-Cases
```js
// JSX ke andar Content badalne ke liye
function LoginButton({ isLoggedIn }) {
  return (
    <button>
      {/* Agar isLoggedIn true hai to 'Logout' dikhega, nahi to 'Login' */}
      {isLoggedIn ? 'Logout' : 'Login'}
    </button>
  );
}
```
```js
// Poora ka poora Component badalne ke liye
function Dashboard({ isAdmin }) {
  return (
    <div>
      <h1>Welcome to Dashboard</h1>
      
      {/* Agar isAdmin true hai to AdminPanel dikhao, nahi to UserPanel */}
      {isAdmin ? <AdminPanel /> : <UserPanel />}
    </div>
  );
}
```
```js
// Dynamic CSS Classes lagane ke liye
function Notification({ isError }) {
  return (
    // Agar isError true hai to background red hoga, nahi to green
    <div className={`alert ${isError ? 'bg-red' : 'bg-green'}`}>
      Message sent successfully!
    </div>
  );
}
```