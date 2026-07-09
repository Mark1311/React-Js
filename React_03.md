# What is the difference between functional and class components?

### Syntax aur Structure:

Functional Components:

* Yeh JavaScript functions hote hain jo props accept karte hain aur UI return karte hain.

* Hooks ke introduction ke baad yeh state aur lifecycle methods ko handle kar sakte hain.


```python
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

```

Class Components:

* Yeh ES6 classes par based hote hain aur React ke lifecycle methods aur state ko handle karte hain.


```python
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

### State Management:

Functional Components:

* Pehle stateless hote the, lekin React Hooks (like useState, useEffect) ke baad functional components mein state aur lifecycle management possible hai.


```python
function Counter() {
  const [count, setCount] = React.useState(0);
  return <button onClick={() => setCount(count + 1)}>Count: {count}</button>;
}

```

Class Components:

* State ko this.state ke through define aur update kiya jata hai using this.setState.


```python
class Counter extends React.Component {
  constructor() {
    super();
    this.state = { count: 0 };
  }
  render() {
    return (
      <button onClick={() => this.setState({ count: this.state.count + 1 })}>
        Count: {this.state.count}
      </button>
    );
  }
}

```

### Lifecycle Methods:


Functional Components:

* Lifecycle methods ka direct support nahi hota, lekin Hooks jaise useEffect se lifecycle events ko handle kar sakte hain.


```python
React.useEffect(() => {
  console.log("Component mounted or updated");
}, [dependency]);

```

Class Components:

* Lifecycle methods ka built-in support hota hai, jaise:

1. componentDidMount

2. componentDidUpdate

3.  componentWillUnmount


```python
class Example extends React.Component {
  componentDidMount() {
    console.log("Component mounted");
  }
  render() {
    return <div>Class Component</div>;
  }
}
```

### Performance

Functional Components:

* Functional components lightweight hote hain, aur hooks ke wajah se cleaner aur faster hote hain.

* Purane React versions mein functional components faster hote the kyunki lifecycle handling nahi hoti thi, lekin ab dono comparable hain.

Class Components:

* Slightly heavier syntax aur this binding ki wajah se thoda complex aur verbose hote hain.

### Readability and Code Size:


Functional Components:

* Code concise aur readable hota hai, especially hooks ke baad.

* Simple use cases ke liye functional components recommend kiye jate hain.

Class Components:

* Code verbose hota hai kyunki constructors, lifecycle methods aur this binding likhna padta hai.



| **Aspect**            | **Functional Components**            | **Class Components**                                   |
| --------------------- | ------------------------------------ | ------------------------------------------------------ |
| **Syntax**            | JavaScript functions                 | ES6 Classes                                            |
| **State Handling**    | Hooks (`useState`, `useEffect`)      | `this.state`, `this.setState`                          |
| **Lifecycle Methods** | `useEffect` for all lifecycle events | Separate lifecycle methods (`componentDidMount`, etc.) |
| **Code Size**         | Concise and readable                 | Verbose and complex                                    |
| **Performance**       | Lightweight and efficient            | Slightly heavier                                       |
| **Usage**             | Recommended for modern React apps    | Used in legacy or existing projects                    |
| **Trend**             | Modern, widely adopted               | Legacy and declining usage                             |


### Interview Tip:

* "Functional components hooks ke saath modern aur clean solution dete hain. Ab React ke most use cases mein functional components hi preferred hain."

* Lekin agar legacy code handle karna ho ya lifecycle methods ko specific tarike se use karna ho, toh class components ka knowledge zaroori hai.

# What is prop drilling?

Prop Drilling ek concept hai React mein, jisme ek component ko data (props) pass karte hue multiple intermediate components ke through jana padta hai, even agar un beech ke components ko woh data directly use karne ki zarurat na ho.

#### Prop Drilling Ka Matlab

Jab parent component ka data kisi deeply nested child component tak pahunchana ho, toh us data (prop) ko hierarchy ke sabhi components ko pass karna padta hai. Ye process tedious aur messy ho sakta hai, especially jab component tree kaafi bada ho.


```python
function App() {
  const userName = "Bittu";

  return <Parent userName={userName} />;
}

function Parent(props) {
  return <Child userName={props.userName} />;
}

function Child(props) {
  return <GrandChild userName={props.userName} />;
}

function GrandChild(props) {
  return <h1>Hello, {props.userName}!</h1>;
}

```

Yahaan App component ka userName prop GrandChild component tak pahunchana tha, lekin har intermediate component (Parent aur Child) ko unnecessary props pass karni pad rahi hai.

### Problems with Prop Drilling:

Unnecessary Complexity:
* Beech ke components ko data pass karna padta hai, chahe unhe zarurat na ho.

Maintainability Issues:
* Agar hierarchy badalti hai, toh sabhi intermediate components ko update karna padta hai.

Code Duplication:
* Bar-bar props ko pass karne ki wajah se repetitive aur verbose code ban jata hai.

### Solutions to Avoid Prop Drilling:

##### Context API:
React ka built-in solution hai, jo data ko directly deeply nested components tak pahunchane deta hai bina intermediate components ke through jaaye.


```python
const UserContext = React.createContext();

function App() {
  return (
    <UserContext.Provider value="Bittu">
      <GrandChild />
    </UserContext.Provider>
  );
}

function GrandChild() {
  const userName = React.useContext(UserContext);
  return <h1>Hello, {userName}!</h1>;
}

```

# What are the different ways to style React components?


| **Method**            | **Advantages**                         | **Disadvantages**                       |
| --------------------- | -------------------------------------- | --------------------------------------- |
| **Inline Styles**     | Quick, simple                          | Hard to maintain, limited CSS support   |
| **CSS Stylesheets**   | Easy to use, reusable                  | Global scope, potential class conflicts |
| **CSS Modules**       | Scoped styles, maintainable            | Slightly more setup                     |
| **Styled Components** | Dynamic styles, no separate files      | Runtime overhead                        |
| **Tailwind CSS**      | Rapid styling, utility-first classes   | Learning curve                          |
| **Emotion**           | Lightweight, flexible                  | Advanced setup                          |
| **SCSS/SASS**         | Nesting, variables, and mixins support | Requires build setup                    |


# What is the difference between controlled and uncontrolled components?
`React me Controlled aur Uncontrolled Components forms/input fields ko handle karne ke 2 tarike hain.`


### 1. Controlled Components

* Definition: Aise components jaha form element ka state React ke control mein hota hai. Form ke values (like input, textarea) ko React state ke zariye manage kiya jata hai.

* Data Flow: React state ek single source of truth hota hai.


```python
function ControlledComponent() {
  const [value, setValue] = React.useState("");

  const handleChange = (e) => {
    setValue(e.target.value);
  };

  return (
    <div>
      <input type="text" value={value} onChange={handleChange} />
      <p>Current Value: {value}</p>
    </div>
  );
}

```

Features:

* React ke state aur UI synchronised hote hain.

* Value directly value attribute aur onChange event ke zariye handle hoti hai.

Pros:

* Predictable aur easier to debug.

* Validation aur data transformation React ke andar hi handle kar sakte hain.

Cons:

* Slightly verbose code.

* Performance issues ho sakte hain agar bohot saare inputs ho.

### 2. Uncontrolled Components

* Definition: Aise components jaha form element ka state React ke control mein nahi hota, balki DOM ka control hota hai. Value ko directly DOM ke reference se access kiya jata hai.

* Data Flow: Data DOM ke andar hi manage hota hai.


```python
function UncontrolledComponent() {
  const inputRef = React.useRef();

  const handleSubmit = () => {
    alert(`Input Value: ${inputRef.current.value}`);
  };

  return (
    <div>
      <input type="text" ref={inputRef} />
      <button onClick={handleSubmit}>Submit</button>
    </div>
  );
}

```

Features:

* Value ref ke zariye directly DOM se fetch ki jati hai.

* React ke state ka involvement nahi hota.

Pros:

* Less boilerplate code.

* Performance better ho sakta hai jab bohot saare inputs ho.

Cons:

* React aur DOM ke beech synchronization nahi hota.

* Validation aur data handling thoda mushkil hota hai.

| **Aspect**           | **Controlled Components**                         | **Uncontrolled Components**                      |
| -------------------- | ------------------------------------------------- | ------------------------------------------------ |
| **State Management** | State React ke control mein hota hai              | State DOM ke control mein hota hai               |
| **Data Flow**        | React state as single source of truth             | DOM element ka internal state use hota hai       |
| **Accessing Values** | `value` attribute aur `onChange` ke zariye        | `ref` ke through DOM se value fetch hoti hai     |
| **Validation**       | React ke andar easy to handle                     | Manual validation karni padti hai                |
| **Code Complexity**  | Slightly verbose                                  | Cleaner and less boilerplate                     |
| **Use Cases**        | Complex forms with validations                    | Simple forms or when direct DOM access is needed |
| **Example Use**      | `<input value={state} onChange={handleChange} />` | `<input ref={inputRef} />`                       |

### Controlled Component vs Uncontrolled Component

| Feature | Controlled Component | Uncontrolled Component |
|----------|----------|----------|
| Definition | Input ki value React State se control hoti hai | Input ki value DOM se control hoti hai |
| Data Store | React State (`useState`) | DOM |
| Control | React ke paas control hota hai | Browser/DOM ke paas control hota hai |
| Hook Used | `useState` | `useRef` |
| Re-render | ✅ Hota hai | ❌ Nahi hota |
| Value Access | State Variable se | `ref.current.value` se |
| Validation | Easy | Thodi Difficult |
| Real-Time Update | ✅ Possible | ❌ Directly Nahi |
| Code Complexity | Thoda Zyada | Thoda Kam |
| Performance | Har change par re-render | Re-render nahi hota |
| Recommended By React | ✅ Haan | Specific Cases me |
| Best Use Case | Forms, Validation, Dynamic UI | File Input, Simple Forms |

##### When to Use?

Controlled Components:

* Jab form ke values aur validations ka control React state ke through karna ho.

* Jab complex forms ho (e.g., multi-step forms, dynamic inputs).

Uncontrolled Components:

* Jab simple forms ya inputs ho.

* Jab DOM ke reference se quick access chahiye (e.g., file upload, legacy code integration).

# How do you apply conditional class names?

```python
//  Using Ternary Operator

function ConditionalClassExample({ isActive }) {
  return (
    <div className={isActive ? "active-class" : "inactive-class"}>
      Conditional Class Example
    </div>
  );
}

// Using Logical Operators

function LogicalClassExample({ isPrimary, isDisabled }) {
  return (
    <button
      className={`button ${isPrimary && "primary"} ${
        isDisabled && "disabled"
      }`}
    >
      Logical Class Example
    </button>
  );
}


// Using Template Literals

function TemplateLiteralExample({ isHighlighted }) {
  return (
    <p className={`text ${isHighlighted ? "highlight" : ""}`}>
      Highlighted Text
    </p>
  );
}
```

| **Method**             | **Advantages**                          | **Disadvantages**                     |
| ---------------------- | --------------------------------------- | ------------------------------------- |
| **Ternary Operator**   | Simple for basic conditions             | Becomes verbose for multiple classes  |
| **Logical Operators**  | Easy to use for multiple conditions     | Less readable in complex logic        |
| **Template Literals**  | Clear syntax for dynamic classes        | Can become messy for multiple classes |


# What is the Context API?


Context API ek React ka built-in feature hai jo components ke beech data ko directly share karne ka solution provide karta hai bina props ko multiple levels tak drill kiye. Iska use global state management ke liye hota hai, jaise ki user authentication, theme settings, ya language preferences.

##### Context API Ka Use Kyun Karte Hain?

Jab aapko ek parent component se deeply nested child component tak data pass karna hota hai, toh aapko har intermediate component ke through props pass karna padta hai. Isse prop drilling hoti hai, jo code ko complex aur difficult to maintain bana deti hai.

* Context API is problem ko solve karta hai by:

1. Data ko globally accessible banana.

2. Intermediate components ko bypass karte hue direct child components tak data pahunchana.



### Context API Ka Workflow

##### Context Create Karna
Ek context object banate hain jo global data ko hold karega.



```python
const ThemeContext = React.createContext();
```

##### Provider Component
Provider component data ko provide karta hai jo context ke andar accessible hoga. Ye top-level component ke around wrap hota hai.


```python
function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}
```

##### Consumer Component
Consumer component context ke data ko access karta hai.


```python
function Toolbar() {
  return (
    <ThemeContext.Consumer>
      {(value) => <div>Current Theme: {value}</div>}
    </ThemeContext.Consumer>
  );
}
```

### Modern Way: useContext Hook


```python
const ThemeContext = React.createContext();

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  const theme = React.useContext(ThemeContext);
  return <div>Current Theme: {theme}</div>;
}

```

Advantages of Context API
* Avoid Prop Drilling: Data ko intermediate components ke beech pass karne ki zarurat nahi hoti.

* Global State Management: User info, theme, language settings jaise global states handle karna easy hota hai.

* Built-in Feature: External library ki zarurat nahi hoti (like Redux or MobX).

Disadvantages of Context API
* Re-rendering Issue: Agar context ka value change hota hai, toh saare consumer components re-render ho jate hain.

* Complexity for Large Applications: For large-scale apps, Redux ya MobX jaise advanced state management tools zyada efficient hote hain.



# Practical Example


```python
const ThemeContext = React.createContext();

function App() {
  const [theme, setTheme] = React.useState("light");

  const toggleTheme = () => {
    setTheme((prevTheme) => (prevTheme === "light" ? "dark" : "light"));
  };

  return (
    <ThemeContext.Provider value={theme}>
      <button onClick={toggleTheme}>Toggle Theme</button>
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  const theme = React.useContext(ThemeContext);
  return <div style={{ background: theme === "light" ? "#fff" : "#333", color: theme === "light" ? "#000" : "#fff" }}>Current Theme: {theme}</div>;
}
```

# What are hooks in React?

`React me hooks ek special function hote hain jo functional components me state aur lifecycle features ko manage karne me madad karte hain. React hooks ko version 16.8 me introduce kiya gaya tha, jisse functional components me class components jaise features use kiye ja sakte hain.`

#### Hooks Ki Definition
* Hooks ek tarika hai jisse functional components me state, lifecycle methods, aur other React features ka use kiya jata hai.

* Hooks ka use karne ke liye React 16.8 ya usse higher version ki zarurat hoti hai.

#### Why Use Hooks?
Hooks se pehle, agar aapko state ya lifecycle methods ka use karna hota tha, toh aapko class components likhne padte the. Class components:

1. Verbose aur complex hote hain.

2. Reusability aur readability mein problem hoti thi.

Hooks:

* Functional components ko lightweight aur reusable banate hain.

* Clean aur simple syntax provide karte hain.


Advantages of Hooks
* Simplified Code: Hooks ke saath functional components ka code zyada readable aur concise hota hai.

* No Class Components Needed: State aur lifecycle features ke liye classes ki zarurat nahi hoti.

* Reusability: Custom hooks bana kar functionality ko share karna easy hota hai.

* Better Testing: Hooks ke saath components test karna zyada straightforward hota hai.

Summary
* Hooks React ke functional components ko state aur lifecycle management ki capability dete hain.

* Common hooks: useState, useEffect, useContext, useReducer.

* Hooks ne React ke development ko modern aur simpler banaya hai, jo ki cleaner syntax aur better reusability provide karta hai.

# Event in React / Event Handler

React mein Event Listener ek function hai jo user ke actions (jaise click, key press, mouse move, etc.) ko detect karta hai aur unke respond mein specific code execute karta hai. Ye React ke event handling system ka ek important part hai.

React ka event system browser ke native DOM events ka wrapper hai, jise Synthetic Events kehte hain. Ye cross-browser compatibility aur performance optimize karta hai.


```python
function ClickExample() {
  function handleClick() {
    alert("Button Clicked!");
  }

  return <button onClick={handleClick}>Click Me</button>;
}

```

How Event Listener Works in React

1. Event Binding:
* React ke andar on<EventName> attribute ke zariye event listener attach kiya jata hai.

2. Synthetic Event:
* React ke events (e.g., onClick, onChange) synthetic events hote hain jo browser ke native events ko wrap karte hain.

3. Function Execution:
* Jab specified event (e.g., click) trigger hota hai, React ka synthetic event listener associated function ko call karta hai.

| **Event Listener** | **Description**                                         |
| ------------------ | ------------------------------------------------------- |
| `onClick`          | Element click hone par trigger hota hai.                |
| `onChange`         | Input ke value change hone par trigger hota hai.        |
| `onSubmit`         | Form submit hone par execute hota hai.                  |
| `onMouseEnter`     | Mouse kisi element ke upar aane par trigger hota hai.   |
| `onMouseLeave`     | Mouse kisi element se bahar jaane par trigger hota hai. |
| `onKeyDown`        | Keyboard key press hone par execute hota hai.           |
| `onFocus`          | Input field focus hone par trigger hota hai.            |
| `onBlur`           | Input field blur hone par trigger hota hai.             |



```python
// 1. Click Event

function ClickEvent() {
  function handleClick() {
    alert("Button Clicked!");
  }

  return <button onClick={handleClick}>Click Me</button>;
}

// 2. Input Change Event


function InputChangeEvent() {
  function handleChange(event) {
    console.log("Input Value:", event.target.value);
  }

  return <input type="text" onChange={handleChange} />;
}

// 3. Form Submit Event


function SubmitEvent() {
  function handleSubmit(event) {
    event.preventDefault(); // Default behavior ko stop karta hai.
    alert("Form Submitted!");
  }

  return (
    <form onSubmit={handleSubmit}>
      <button type="submit">Submit</button>
    </form>
  );
}
// 4. Mouse Events


function MouseEvent() {
  function handleMouseEnter() {
    console.log("Mouse Entered!");
  }

  function handleMouseLeave() {
    console.log("Mouse Left!");
  }

  return (
    <div onMouseEnter={handleMouseEnter} onMouseLeave={handleMouseLeave}>
      Hover Over Me!
    </div>
  );
}
```

# What is React Fiber?


React Fiber ek React ka underlying reconciliation algorithm hai, jo React applications ke UI rendering aur updates ko manage karne ke liye use hota hai. Fiber ko React 16 se introduce kiya gaya tha, aur iska goal tha React ko fast, smooth, aur modern applications ke liye efficient banana.

`State Change → React re-render → New Virtual DOM representation → Fiber/Reconciliation changes find karta hai → Commit Phase → Real DOM update `

#### React Fiber Kya Hai?
* React Fiber ek reconciliation engine hai jo UI rendering aur updates ke process ko optimize karta hai.

* Iska primary focus hai large and complex UIs ke liye better performance ensure karna, especially animations, transitions, or interactions ke liye.

* Ye ek incremental rendering system hai jo rendering tasks ko chhoti-chhoti units (fibers) mein tod deta hai, jisse app responsive lagti hai.

#### Why React Fiber?
Traditional React reconciliation algorithm synchronous tha, matlab jab React koi update karta tha, toh wo saare tasks complete hone tak JavaScript thread ko block kar deta tha. Ye large UIs ke liye performance issues create karta tha.

React Fiber:

* Rendering ko asynchronous banata hai (interruptible rendering).

* User interactions ke liye responsiveness improve karta hai.

* Animations aur transitions smooth banata hai.

#### Key Features of React Fiber

1. Incremental Rendering
* Fiber algorithm rendering tasks ko chhoti-chhoti parts mein todta hai, aur unhe ek priority ke basis par execute karta hai.

* High-priority tasks: User interactions, animations, etc.

* Low-priority tasks: Background data fetching, non-visible updates, etc.

* Ye approach cooperative scheduling kehlaata hai, jisme React important tasks pehle complete karta hai aur baaki kam-priority tasks baad mein.

2. Interruptible Rendering
* Fiber rendering process ko interrupt hone ki permission deta hai, jisse React higher-priority tasks ko handle kar sakta hai.

For example:

* Agar ek user scroll kar raha hai aur simultaneously state update ho raha hai, toh React pehle scrolling ko prioritize karega aur state update baad mein karega.

3. Better Reconciliation
* Fiber reconciliation kaafi granular aur efficient hai:

* Ye diffing process mein sirf updated parts ko re-render karta hai, na ki poore tree ko.

* Isse performance improve hoti hai.

4. Backward Compatibility
* Fiber React ke purane versions ke saath backward compatible hai, jisme developers ko apne existing codebase mein koi changes karne ki zarurat nahi hoti.

#### Advantages of React Fiber
1. Smooth Animations and Transitions
* Fiber UI updates ke liye incremental rendering approach use karta hai, jo animations aur transitions ko smooth banata hai.

2. Improved Performance
* Interruptible rendering ke wajah se high-priority tasks delay nahi hote.

3. Better User Experience
* User interactions responsive lagte hain, kyunki React sabse pehle user ke actions handle karta hai.

4. Scalability
* Large UIs ke liye React Fiber zyada efficient hai.

# What are custom hooks and why are they useful?


Custom Hooks React ke functional components me reusable logic likhne ka ek tarika hai. Agar aapke multiple components mein same logic repeat ho raha hai (e.g., state management, API calls, subscriptions), toh aap is logic ko ek custom hook ke roop me extract kar ke reuse kar sakte hain.

#### Custom Hooks Kya Hain?
1. Custom Hook ek JavaScript function hai jo use se start hota hai (e.g., useFetch, useCounter).

2. Ye React ke built-in hooks ka use karke ek encapsulated logic provide karta hai.

3. Ye stateful logic ko functional components ke beech share karna easy banata hai.

#### Custom Hooks Ka Structure
Custom hook kaafi similar hota hai functional component se:

* Ye ek function hota hai jo hooks ka use karta hai.

* Ye component ke andar state aur side-effects ko manage karta hai.

* Isme logic reusable hota hai.


```python
import { useState } from "react";

function useCounter(initialValue = 0) {
  const [count, setCount] = useState(initialValue);

  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);

  return { count, increment, decrement };
}

export default useCounter;

```


```python
function CounterComponent() {
  const { count, increment, decrement } = useCounter(10);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
    </div>
  );
}

```

##### Why Custom Hooks Are Useful
1. Reusability
* Custom hooks allow logic reuse across multiple components.

* DRY (Don't Repeat Yourself) principle ko follow karte hain.

2. Cleaner Code
* Complex logic ko hooks me encapsulate karke component ka code simpler aur readable banata hai.

3. Separation of Concerns
* Business logic ko component ke UI logic se separate karne me help karta hai.

4. Testability
* Custom hooks ko isolate karke test karna easy hota hai.

5. State and Side Effect Management
* Aap state aur side effects ko ek saath manage kar sakte hain.

| **Aspect**           | **Custom Hook**                                           | **Normal Function**                              |
| -------------------- | --------------------------------------------------------- | ------------------------------------------------ |
| **Stateful Logic**   | Stateful logic handle karta hai                           | Stateless hota hai                               |
| **React Dependency** | Built-in hooks ka use karta hai                           | Hooks ka use nahi karta                          |
| **Reusability**      | Logic ko multiple components me reuse karta hai           | Stateless functions me sirf logic reuse hota hai |
| **React Lifecycle**  | Lifecycle methods ka support deta hai (e.g., `useEffect`) | Lifecycle methods nahi hote                      |


# Common Causes of Unnecessary Re-renders


| **Cause**                              | **Solution**                                  |
| -------------------------------------- | --------------------------------------------- |
| Parent component re-renders            | Use `React.memo` or optimize parent logic.    |
| Non-memoized functions passed as props | Use `useCallback` for functions.              |
| State updates causing re-renders       | Avoid deep state mutations, use `useReducer`. |
| Arrays/objects passed as props         | Use `useMemo` to memoize arrays/objects.      |
| Incorrect dependency arrays            | Ensure proper `useEffect` dependencies.       |


# What are keys in React and why are they important?

Keys React me ek unique identifier hote hain jo React ko batate hain ki ek list me kaunsa item change, add, ya remove hua hai. Ye mainly dynamic lists ke liye use hote hain aur React ke reconciliation process me important role play karte hain.

`React me "key" ek special prop hota hai jo list items ko uniquely identify karne ke liye use hota hai. Jab aap kisi list ko render karte ho (jaise map() method se), toh React ko pata hona chahiye ki kaunsa item update hua hai, kaunsa item delete hua hai, ya kaunsa item add hua hai. Isliye key ka use kiya jata hai.`

Keys Kya Hain?
* Keys ek unique identifier hote hain jo map(), lists, ya dynamic elements ke saath use hote hain.

* Ye React ko efficiently DOM updates karne me madad karte hain by uniquely identifying elements.

```jsx
const items = ["Apple", "Banana", "Cherry"];

function ItemList() {
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
}

const products = [
  { id: 1, name: 'Laptop', price: 50000 },
  { id: 2, name: 'Phone', price: 30000 },
  { id: 3, name: 'Headphones', price: 5000 }
];

const ProductList = () => {
  return (
    <ul>
      {products.map((product) => (
        <li key={product.id}>
          {product.name} - ${product.price}
        </li>
      ))}
    </ul>
  );
};

```

Keys Kyun Zaroori Hain?

Efficient Updates:
* React keys ki help se identify karta hai ki kaunsa list item modify, add, ya delete hua hai.

Performance Optimization:
* Agar unique keys na ho, toh React puri list ko re-render kar dega, jo performance degrade kar sakta hai.

Avoid UI Bugs:
* Galat ya missing keys unpredictable behavior ya rendering issues cause kar sakti hain.

React Keys Ka Importance Reconciliation Mein

React ke Virtual DOM me jab koi update hota hai, toh React changes ko efficiently apply karta hai:

Keys ke bina:
* React puri list ko destroy aur dubara render karta hai.

Keys ke sath:
* React sirf usi list item ko update karta hai jo badla hai.

#### Key aur Re-rendering:
React ko jab list me changes dekhna hote hain (jaise item add ya remove ho), toh wo virtual DOM me check karta hai ki kis item ka position change hua hai. Agar key sahi se set ki gayi ho, toh React ko pata chal jata hai ki kis item ko update karna hai, bina poore list ko dobara render kiye. Isse rendering fast hota hai.

#### Key ka Importance:
Jab aap React me list items render karte hain (jaise map() function se), toh React ko yeh samajhna hota hai ki har item ka unique identity kya hai, taki wo efficiently update kar sake jab state ya props change ho. Agar aap key ka sahi tareeke se use nahi karte, toh React ko har item ko re-render karna padta hai, jo unnecessary performance cost hota hai.

Agar aap key nahi provide karte, toh React default behavior me index ko key samajh kar use karta hai. Lekin yeh problem create kar sakta hai agar aapki list me items ka order change ho, ya items add/remove ho.


# How do you optimize performance in a React app?


Use React.memo

* Prevents unnecessary re-renders of functional components when props haven't changed.

Use useCallback

* Memoizes functions to avoid creating new references on each render.

Use useMemo

* Memoizes expensive computations to avoid recalculating on every render.

Code Splitting

* Dynamically load components with React.lazy and React.Suspense to reduce initial bundle size.

Virtualize Long Lists

* Use libraries like react-window or react-virtualized to render only visible list items.

Optimize Images

* Use compressed images, lazy loading, and modern formats like WebP.

Avoid Inline Functions in JSX

* Define event handlers outside JSX to prevent new function creation on every render.

Optimize State Management

* Minimize state updates and avoid deeply nested state.

Avoid Unnecessary Re-renders

* Use React.memo for child components and optimize parent state.

Use Production Build

* Deploy apps using npm run build for optimized performance.

Remove Console Logs

* Clean up debugging statements before deploying.

Use Static Content Memoization

* Memoize static values or use constants for unchanging data.

Batch State Updates

* React automatically batches state updates, but ensure you don't split them unnecessarily.

Virtual DOM Keys

* Always use unique keys for lists to optimize reconciliation.

Optimize CSS and Styles

* Avoid inline styles; prefer CSS-in-JS libraries or precompiled CSS.

# What is the difference between <Link> and <a> in React Router?


| **Aspect**          | **`<Link>`**                                                                                       | **`<a>`**                                                                             |
| ------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Purpose**         | Used for navigation within a React Router app without refreshing the page.                         | Used for navigation to any URL, including external links, causing a full page reload. |
| **Behavior**        | Prevents the default page reload by leveraging React Router's client-side routing.                 | Triggers a full-page reload by default.                                               |
| **Performance**     | More efficient as it doesn’t reload the page and only updates the necessary part of the UI.        | Less efficient due to complete page reload, losing the current state of the app.      |
| **Routing Context** | Works with the React Router's routing context to navigate between routes.                          | Doesn't interact with React Router; relies on the browser's default behavior.         |
| **Usage Scenario**  | For internal navigation within the app's defined routes.                                           | For external links or scenarios where a full page reload is required.                 |
| **Props Support**   | Accepts React Router-specific props like `to`, `replace`, and `state`.                             | Supports standard HTML anchor attributes like `href`, `target`, and `rel`.            |
| **State Passing**   | Allows passing state through `to` prop (e.g., `{ pathname: "/about", state: { data: "value" } }`). | Cannot pass state directly; only uses query parameters or URL fragments.              |



```python
import { Link } from "react-router-dom";

function Navigation() {
  return (
    <nav>
      <Link to="/home">Home</Link>
      <Link to="/about">About</Link>
    </nav>
  );
}

```

No page reload.

Optimized for React Router's client-side navigation.

function ExternalLink() {
  return (
    <a href="https://www.example.com" target="_blank" rel="noopener noreferrer">
      Visit Example
    </a>
  );
}


Page reloads when clicked.

Suitable for linking to external websites.

# How did you make API calls in your project?


####  Using fetch()


```python
import React, { useState, useEffect } from "react";

function FetchExample() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/posts")
      .then((response) => response.json()) // Convert response to JSON
      .then((data) => {
        setData(data);
        setLoading(false);
      })
      .catch((error) => console.error("Error fetching data:", error));
  }, []);

  if (loading) return <p>Loading...</p>;

  return (
    <ul>
      {data.map((post) => (
        <li key={post.id}>{post.title}</li>
      ))}
    </ul>
  );
}

export default FetchExample;

```

####  Using Axios 


```python
import React, { useState, useEffect } from "react";
import axios from "axios";

function AxiosExample() {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    axios
      .get("https://jsonplaceholder.typicode.com/posts")
      .then((response) => {
        setData(response.data); // Axios automatically parses JSON
        setLoading(false);
      })
      .catch((error) => console.error("Error fetching data:", error));
  }, []);

  if (loading) return <p>Loading...</p>;

  return (
    <ul>
      {data.map((post) => (
        <li key={post.id}>{post.title}</li>
      ))}
    </ul>
  );
}

export default AxiosExample;

```

#### Using Async/Await for Cleaner Syntax


```python
import React, { useState, useEffect } from "react";

function AsyncAwaitExample() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch("https://jsonplaceholder.typicode.com/posts");
        const result = await response.json();
        setData(result);
      } catch (error) {
        console.error("Error fetching data:", error);
      } finally {
        setLoading(false);
      }
    };

    fetchData();
  }, []);

  if (loading) return <p>Loading...</p>;

  return (
    <ul>
      {data.map((post) => (
        <li key={post.id}>{post.title}</li>
      ))}
    </ul>
  );
}

export default AsyncAwaitExample;

```

# What is the React.memo()?

React.memo() ek higher-order component (HOC) hai jo functional components ko optimize karne ke liye use hota hai. Yeh component ko wrap karke unnecessary re-rendering ko prevent karta hai agar uske props same hain. Matlab, agar props mein koi change nahi hai, toh component dubara render nahi hoga.

Definition:

React.memo() ek performance optimization tool hai jo React functional components ke liye hai. Agar parent component re-render hota hai, toh child component sirf tabhi re-render hoga jab uske props badlenge.


```python
const MemoizedComponent = React.memo(OriginalComponent);
```

#### Kaise Kaam Karta Hai?
Props Compare Karta Hai: React.memo() automatically shallow comparison karta hai props ka.

Same Props Ke Liye Render Skip Karega: Agar props same hain, toh component dubara render nahi karega.

Different Props Ke Liye Render Karega: Agar props badalte hain, toh normal re-render hoga.




```python
function ChildComponent({ name }) {
  console.log("Child rendered");
  return <div>Hello, {name}!</div>;
}

function ParentComponent() {
  const [count, setCount] = React.useState(0);

  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Increment</button>
      <ChildComponent name="John" />
    </div>
  );
}

```

##### Kab Use Karein?
Jab functional components heavy calculations karte ho aur baar-baar render karne ki zarurat na ho.

Jab props rarely change hote hain.

Jab performance optimization required ho.


# How do you optimize performance in a React app?

1. Component Re-Rendering Ko Control Karein

React.memo() ka use karein functional components ke unnecessary re-render ko rokne ke liye.

Class components ke liye PureComponent ka use karein.

2. State Management Ko Optimize Karein

State share karne ke liye lifting state up ka use karein.

Context API ka overuse avoid karein, kyunki yeh multiple components ko re-render kara sakta hai.

3. Code-Splitting with Lazy Loading

Components ko dynamically load karne ke liye React.lazy() aur Suspense ka use karein.

4. Virtualization for Long Lists

Large lists ke liye React Virtualized ya React Window libraries ka use karein, jo sirf visible items render karti hain.

5. Inline Functions Ko Avoid Karein

useCallback ka use karke event handlers ko memoize karein, taki unnecessary re-renders na ho.

6. Expensive Computations Optimize Karein

useMemo ka use karein expensive calculations ke result ko memoize karne ke liye.

useCallback ka use karein functions ke reference ko memoize karne ke liye.

7. Images Optimize Karein

Lazy loading aur compressed formats jaise WebP ka use karein.

8. Code Ko Minify aur Bundle Karein

Webpack ya Vite ka use karke JavaScript aur CSS ko minify karein aur bundle karein.

9. Production Build Use Karein

Deployment ke liye production build (npm run build) ka use karein, jo zyada optimized hoti hai.

10. Server-Side Rendering (SSR)

Frameworks jaise Next.js ka use karke content ko server-side render karein, jo faster loading provide karta hai.

11. User Input Debounce/Throttle Karein

Heavy operations jaise search ke liye debounce ya throttle ka use karein, taki performance better ho.

12. Avoid Large Bundle Sizes

Use tree-shaking to remove unused code during the bundling process.

Import only the required parts of libraries (e.g., lodash-es instead of lodash).

13. Use React DevTools Profiler

React DevTools ka Profiler use karke identify karein ki kaunse components frequently re-render ho rahe hain aur optimization ki zarurat hai.

14. Implement Error Boundaries

Error Boundaries ka use karke app ko crash hone se bacha sakte hain aur performance ko impact hone se rok sakte hain.

15. Optimize Event Listeners

Event listeners ko throttle/debounce karein aur unmount hone par cleanup zaroor karein.

16. Optimize CSS

Use CSS-in-JS libraries like Emotion or Styled Components for dynamic styling.

Avoid unused CSS aur Critical CSS implement karein.

17. Keep Components Small and Reusable

Large components ko chhote functional components mein divide karein.

Reusability badhane ke liye shared components ka use karein.

18. Optimize Third-Party Libraries

Avoid unnecessary libraries.

Check for lightweight alternatives or only import what’s needed.

19. Use Web Workers for Heavy Computations

Heavy computations ko main thread se hatane ke liye Web Workers ka use karein.

20. Optimize API Calls

API responses ko cache karein aur pagination implement karein.

Use libraries like React Query or SWR for efficient data fetching.

21. Use Static Assets Efficiently

Static assets ko CDN (Content Delivery Network) par host karein.

Proper caching strategies implement karein.

22. Prevent Memory Leaks

useEffect cleanup functions ka use karein to prevent memory leaks.

# What is Webpack in React?

Webpack ek popular module bundler hai jo React applications ko efficiently manage aur optimize karne ke liye use hota hai. Yeh different files (JavaScript, CSS, images, etc.) ko ek single bundled file ya multiple optimized files mein combine karta hai, jo browser ke liye load karna easy hota hai.

Webpack Ka Role in React:

1. Code Bundling:

Webpack React ke alag-alag modules ko ek single file mein bundle karta hai.

Yeh React apps ko efficiently deploy karne mein madad karta hai.

2. Module Handling:

JavaScript ke alawa CSS, images, fonts, aur other assets ko bhi manage karta hai.

3. Hot Module Replacement (HMR):

Development ke time changes ko real-time mein browser par reflect karta hai bina poore app ko reload kiye.

4. Tree Shaking:

Unused code ko automatically remove karta hai, jo final bundle size reduce karta hai.

5. Plugins Aur Loaders:

Webpack ko customize karne ke liye plugins aur loaders ka use hota hai, jisme CSS, images, aur transpiling ke liye specific tools integrate hote hain.

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

| Feature / Khoobi | React State (`useState`) | Normal Variable (`let`, `const`) |
| :--- | :--- | :--- |
| **Component Re-rendering** | Jab bhi state ki value badalti hai, React component automatically **re-render** hota hai aur screen par naya data dikhta hai. | Variable ki value badalne par component **re-render nahi hota** aur screen par purani value hi dikhti rehti hai. |
| **Data Persistence (Data ka tikna)** | Re-render hone ke baad bhi state apni purani value ko **yaad rakhta hai** (data loss nahi hota). | Har naye re-render par variable **re-initialize (reset)** ho jata hai, jis se uski badli hui value khoti (loss) jati hai. |
| **Value Update Karne Ka Tarika** | Isse direct update nahi kar sakte. Iske liye `setState` function (jaise `setCount`) ka use karna padta hai. <br>`setCount(5)` | Isse aap normal assignment operator (`=`) se direct update kar sakte hain. <br>`count = 5` |
| **Asynchronous Nature** | State updates **asynchronous** hote hain, yaani value turant agli hi line me update nahi hoti, thoda waqt leti hai. | Variable updates **synchronous** hote hain, value turant agli hi line me update ho jati hai. |
| **Main Purpose (Upyog)** | Iska use tab kiya jata hai jab hume koi aisa data store karna ho jo screen/UI par dynamic badlav dikhaye (e.g., Counter, Form Input, Dark Mode toggle). | Iska use temporary calculations, loops, ya static data (jo kabhi nahi badlega) ko store karne ke liye kiya jata hai. |


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
