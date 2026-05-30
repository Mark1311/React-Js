# Promise:-

Imagine aapke paas ek magic lamp hai jisme ek genie (Promise) rehta hai. Ab jab aap us genie ko bulane ki koshish karte ho (promise call karte ho), toh genie turant kaam nahi karta. Genie aapko kehta hai, “Chill karo, mai kaam kar raha hoon, thoda time lagega.”

* Step 1: Promise is called
Jab aap ek promise banate ho, toh browser ko ek kaam diya jata hai jo future mein hoga. Samjho aapne ek ice cream order ki (yeh promise call hai). Lekin ice cream toh abhi milne waali nahi hai, toh aap wait karte ho.
Is samay, aapka browser bolega "OK bhai, yeh kaam pending hai." Browser ke andar ek special system hota hai jisko event loop kehte hain. Yeh event loop track karta hai ki kaunse kaam abhi pending hain aur kaunse complete ho gaye hain.

* Step 2: Promise is pending
Abhi tak, ice cream nahi aayi hai, toh browser kehta hai yeh promise “pending” state mein hai. Matlab kaam ho raha hai, lekin abhi tak complete nahi hua. Aap chill kar rahe ho aur doosre kaam kar rahe ho, jaise TV dekh rahe ho.
Browser ke andar, JavaScript ko ek call stack mein daal diya jata hai jab wo ek promise ko execute karta hai. Lekin promise ka actual kaam call stack se nikal kar ek alag jagah chale jata hai jisko Web APIs bolte hain. Yeh Web APIs ka system kaam ko parallelly handle karta hai, taaki aapke browser mein aur kaam ruk na jaye.

* Step 3: Job Queue
Jab browser ko pata chal jata hai ki ice cream ready hone wali hai, toh wo ek queue mein (isko microtask queue ya job queue bolte hain) kaam ko daal deta hai. Job queue mein wo kaam hota hai jo promises ya microtasks ke liye ready hota hai.

* Step 4: Promise Resolved or Rejected
Ab genie apna kaam complete karta hai aur ice cream deliver ho jaati hai. Ab yeh promise "resolved" ho gaya hai. Agar kuch gadbad hoti hai, jaise ice cream gir gayi, toh yeh promise "rejected" ho jayega.
Jab promise resolved ho jaata hai, event loop check karta hai ki job queue mein koi kaam pending hai kya. Agar kuch hai, toh browser use utha ke execute karta hai. Aapko ice cream mil jaati hai (promise fulfilled), ya phir aapko bataya jaata hai ki ice cream nahi aayi (promise rejected).


# Conditional Handeling

Conditional handling in React refers to the practice of rendering different UI elements based on certain conditions. It allows developers to display content dynamically based on a state, props, or any other conditions that change during the app’s lifecycle.


```python
// ##### Using if statements:

function Welcome(props) {
  if (props.isLoggedIn) {
    return <h1>Welcome back!</h1>;
  } else {
    return <h1>Please sign up.</h1>;
  }
}

// ##### Using Ternary Operators:

function Welcome(props) {
  return (
    <h1>{props.isLoggedIn ? 'Welcome back!' : 'Please sign up.'}</h1>
  );
}

// ##### Using Logical && Operator

function Greeting(props) {
  return (
    <div>
      {props.isLoggedIn && <h1>Welcome back!</h1>}
    </div>
  );
}
```

# useReducer Hook's

useReducer React ka ek hook hai jo state management ke liye use hota hai, khaas kar jab aapko complex state logic ko handle karna ho, ya jab aapko ek se zyada values ko ek saath manage karna ho ek single state object mein.

Jab aapko useState ke sath state ko update karne ki zarurat ho, to aap simple updates ke liye use karte hain. Lekin agar aapko ek complex state ko multiple actions ke through manage karna ho, jaise kisi state ko ek sequence of actions ke through update karna, to useReducer ka use hota hai.


```python
// #Syntax:-

const [state, dispatch] = useReducer(reducer, initialState);
```

* state: Yeh wo current state hoti hai jo aapke component mein hoti hai.
* dispatch: Yeh ek function hai jo actions ko trigger karta hai jisse state update hoti hai.
* reducer: Yeh ek function hai jo state aur action ko input leta hai aur ek naya state return karta hai.
* initialState: Yeh wo initial state hoti hai jo component pehli baar render hota waqt set hoti hai.

##### Key Points:
* useReducer ko complex state updates handle karne ke liye use kiya jata hai.
* Yeh ek reducer function use karta hai jo state aur action ko accept karke naya state return karta hai.
* dispatch function actions ko trigger karta hai, jo reducer ke through state ko update karta hai.

React mein useState() toh sabko pata hai, right? But jab state ka structure thoda heavy ho, ya actions multiple hon ya complex ho, tab useReducer() hero ban ke aata hai! 

Imagine karo, tumhare ghar mein ek almari hai (state) jisme bahut saare compartments hain (different pieces of state). Ab agar tum har ek compartment ko alag key se unlock kar rahe ho (useState()), toh cheezein thodi messy ho sakti hain. Isliye hum useReducer() ko bulaate hain, jo ek saath ek "remote" de deta hai. Bas ek button press karo, aur desired action perform ho jaaye! 

Toh exactly hota kya hai?

1. Reducer Function: Ek function jo decide karega ki kaunsi action ka result kya hoga. Jaise ek manager jo sab decisions le raha ho.

2. Dispatch: Tumhara ek command center jahan se tum batate ho kya karna hai, action type bhejke.

Ab samjho ki tum ek form banate ho, jisme user ka naam, email, aur address store karna hai. Sab ke liye useState() lagane ki jagah, tum ek useReducer() use kar sakte ho, jo action ke hisaab se saari state ko manage karega.

useReducer() basically kaam karta hai jab tumhare pass zyada complex state management ho, ya jab tumhe alag-alag actions perform karni ho, jaise ek restaurant mein waiter ko alag-alag tables ka order dena ho. 


# useCallback Hook's

useCallback ek React hook hai jo function references ko memoize karne ke liye use hota hai, jisse unnecessary re-renders ko avoid kiya jaa sakta hai. Jab bhi aap kisi function ko component ke andar define karte hain, wo har render par nayi reference create karta hai, jo React ko lagta hai ke wo function change ho gaya hai, aur iske kaaran component ko unnecessary re-render karna padta hai.

useCallback hook, function ke reference ko memoize karke is problem ko solve karta hai. Jab function ka dependency change nahi hota, to wo same reference return karta hai, jisse React ko unnecessary re-renders ka pata nahi chalta.


```python
// ## Syntax:-

const memoizedCallback = useCallback(() => {
  // function logic
}, [dependencies]);
```

##### Kab use karein useCallback?
Agar aapke paas callback functions hain jo child components ko pass kiye ja rahe hain, aur aap nahi chahte ki wo child components har render pe re-render ho.

Jab aapke function ke dependencies nahi badal rahe ho, tab useCallback ka use karke aap function ko memoize kar sakte hain, taake unnecessary re-renders avoid ho sakein.

##### useCallback ka basic concept:
Jab aap kisi function ko component ke andar define karte hain, wo function har baar re-render hone par naya reference bana leta hai. Agar aapne wo function kisi child component ko pass kiya ho, to child component ko har re-render par lagta hai ki us function ka reference change ho gaya hai, aur isliye wo child component bhi re-render ho jata hai. Yeh unnecessary re-renders performance ko slow kar sakte hain, khaas kar jab aapke paas complex components ho ya un components ko frequently re-render kiya jata ho.

##### useCallback ka main kaam hai:

* Function ka reference memoize karna, yaani agar us function ka dependency change nahi hua hai, to wo same reference ko return karega.

* Isse aap unnecessary re-renders avoid kar sakte hain, aur performance improve hoti hai.

##### useCallback ka Kaise kaam karta hai?
Jab aap useCallback ko use karte hain, to yeh function ko memoize karta hai. Aur jab tak aapke useCallback ke dependency array mein koi change nahi hota, tab tak function ka reference same rahega

#### Real-World Example:
Maan lijiye aapke paas ek large form hai jisme multiple input fields hain, aur har input field apne aap mein ek component hai. Har input field ke saath ek callback function attached hai jo form ke state ko update karta hai.

Agar aap har input ke function ko bina useCallback ke pass karte hain, to har re-render pe functions ka naya reference create hoga, jisse form ke components unnecessarily re-render honge. Is situation mein useCallback ka use karke aap unnecessary re-renders ko avoid kar sakte hain aur app ki performance ko optimize kar sakte hain.

# Example:-


```python
// # Example without useCallback:-

import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  // Simple function to increment the count
  const increment = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}

export default Counter;
```


```python
// # Example with useCallback:-

import React, { useState, useCallback } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  // Memoize the increment function using useCallback
  const increment = useCallback(() => {
    setCount(count + 1);
  }, [count]); // Dependency array

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={increment}>Increment</button>
    </div>
  );
}

export default Counter;
```

##### Kya changes kiye?
* Humne increment function ko useCallback ke andar wrap kiya.
* useCallback function ko ek dependency array diya ([count]), jo batata hai ki jab count change hoga, tabhi increment function ko update karna hai.
* Ab, jab tak count value change nahi hoti, increment function ka reference same rahega, aur unnecessary re-renders nahi honge.

##### Difference:
* Without useCallback: Har render par naya function create hota hai.
* With useCallback: Function ka reference memoize ho jaata hai aur unnecessary re-renders avoid hote hain.

# UseNavigate Hook's

useNavigate hook React Router v6 mein introduced hua hai. Ye hook aapko programmatically navigation (routing) karne ki suvidha deta hai. Iska use aap React components ke andar kar sakte hain, jab aapko user ko ek route se dusre route par le jana ho bina traditional <a> tag ya Link component ke.

Jab aap useNavigate ko call karte hain, ye aapko ek navigate function deta hai, jo aapko specific route par navigate karne mein help karta hai.


```python
import React from 'react';
import { useNavigate } from 'react-router-dom';

const MyComponent = () => {
  const navigate = useNavigate();

  const handleClick = () => {
    // Programmatically navigate to the '/home' route
    navigate('/home');
  };

  return (
    <div>
      <button onClick={handleClick}>Go to Home</button>
    </div>
  );
};

export default MyComponent;
```

* useNavigate() hook se navigate function milta hai.
* Jab user button click karega, navigate('/home') function call hota hai, jo /home route par navigate kar deta hai.


```python
// # Syntax:-

const navigate = useNavigate();
navigate('/path');
```

### React-router or useNavigate me kya diff:-

##### React Router:
React Router ek library hai jo aapko client-side routing ki suvidha deti hai React applications mein. Iska main kaam URLs ko handle karna hai, jaise ki aap different components ko URL ke hisaab se render kar sakein bina page ko reload kiye.

React Router mein Route, BrowserRouter, Link, aur Outlet jaise components hote hain jo routing ko manage karte hain.


```python
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';

const App = () => (
  <Router>
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  </Router>
);
```

##### useNavigate:
useNavigate ek hook hai jo React Router v6 ka part hai. Ye aapko programmatically navigation karne ki suvidha deta hai. Matlab agar aapko kisi event (button click, form submit, etc.) ke basis par routing karni ho, toh aap useNavigate hook ka use karte hain.

React Router ka useNavigate hook aapko ek navigate function deta hai, jiska use aap specific route pe navigate karne ke liye kar sakte hain.


```python
import { useNavigate } from 'react-router-dom';

const MyComponent = () => {
  const navigate = useNavigate();

  const handleClick = () => {
    // Programmatically navigate to the '/about' route
    navigate('/about');
  };

  return <button onClick={handleClick}>Go to About</button>;
};
```

##### Summary of the Difference:
1.React Router ek routing library hai jo URLs aur components ko handle karta hai.
* Routes ko define karta hai jaise <Route path="/about" element={<About />} />.
* Aap URL ke basis par components render karne ke liye use karte hain.

2. useNavigate ek hook hai jo React Router v6 ka part hai aur aapko programmatically navigate karne ki suvidha deta hai.
* Aap button click, form submission, ya kisi other event ke basis par route change karne ke liye use karte hain.

`// Use this to go back to previeous page or 
location navigate(-1);`

# UseContext and ContextAPI?

useContext React ka ek hook hai jo functional components mein context ka use karne ke liye istemal hota hai. Iska primary purpose yeh hai ke aap global state ya data ko apne component tree mein asani se pass kar sakein, bina props drilling (yaani props ko ek component se doosre component tak manually pass karne) ke.

### useContext ka use kaise hota hai?

##### Context Create Karna: Sabse pehle aapko createContext se ek context create karna padta hai.


```python
import React, { createContext, useState } from 'react';

const MyContext = createContext();
```

##### Context Provider ka use karna: 
Aap apne root component ya kisi bhi parent component mein MyContext.Provider ko wrap karte hain jisme value ko define karte hain.


```python
function App() {
  const [count, setCount] = useState(0);

  return (
    <MyContext.Provider value={{ count, setCount }}>
      <ChildComponent />
    </MyContext.Provider>
  );
}
```

##### useContext ka use karna: 
Ab jab aapko kisi child component mein context ki value chahiye, to aap useContext hook ka use karte hain.


```python
function ChildComponent() {
  const { count, setCount } = useContext(MyContext);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

#### useContext ka fayda:

* Props Drilling se bachna: 
Agar aapke paas deep nested components hain, to context ki madad se aap kisi bhi component mein easily value access kar sakte hain, bina har level pe props pass kiye.

* Simpler code: 
useContext se code kaafi clean aur simple ho jata hai, kyunki aapko props chaining ki zarurat nahi hoti.

# Diff between UseContext and ContextAPI:-

#### 1. Context API:
The Context API in React is a way to share values between components without having to explicitly pass props down the component tree. It allows you to create global variables that can be accessed by any component that is a descendant of the context provider.

* React.createContext(): This function creates a context object.

* Context.Provider: This component is used to provide the context value to its descendants.

* Context.Consumer: This component is used to consume the context value in class components (before hooks were introduced).

##### 2. Context Hooks:
React introduced hooks in version 16.8, which also includes hooks for working with Context API. These hooks make it easier to consume context values without having to use the Context.Consumer component.

* useContext(): This hook is used to access the context value in functional components.

# Example:-


```python
import React, { createContext, useContext, useState } from 'react';

// 1. Create Context
const BiryaniContext = createContext();

// 2. Provider
const BiryaniProvider = ({ children }) => {
 const [ingredient, setIngredient] = useState("Rice");
 return (
 <BiryaniContext.Provider value={{ ingredient, setIngredient }}>
 {children}
 </BiryaniContext.Provider>
 );
};

// 3. Consumer using Context
const BiryaniConsumer = () => {
 const { ingredient, setIngredient } = useContext(BiryaniContext);
 return (
 <div>
 <h1>Ingredient: {ingredient}</h1>
 <button onClick​={() => setIngredient("Chicken")}>Add Chicken</button>
 </div>
 );
};

// 4. Main App
const App = () => (
 <BiryaniProvider>
 <BiryaniConsumer />
 </BiryaniProvider>
);

export default App;


```

Imagine karo tum ek biryani ki recipe bana rahe ho (Provider). Tumhare saare dost (Consumers) tumhare ingredients ka wait kar rahe hain, but instead of individually giving each one the ingredients (prop drilling), tum ek note bana kar sabko ek hi baar broadcast kar dete ho (Context API). Sabko biryani mil gayi!

# Event in React / Event Handler

React mein "event" ek interaction hota hai jo user ne kisi element ke saath perform kiya ho, jaise button click karna, form submit karna, mouse hover karna, ya keyboard key press karna. React events kaafi similar hote hain browser ke native events ke, lekin React mein ye thoda alag tarike se handle hote hain.

React mein events ko handle karne ke liye hum event handler functions ka use karte hain. Ye event handler functions React components ke andar define kiye jaate hain aur unko specific DOM elements ke saath bind kiya jata hai.

#### Simple Example:-


```python
import React, { useState } from 'react';

function App() {
  const [count, setCount] = useState(0);

  const handleClick = () => {
    setCount(count + 1);
  };

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={handleClick}>Click me</button>
    </div>
  );
}

export default App;
```

# Component Life Cycle:-

Component Life Cycle React (aur aise hi baaki framework) mein ek process hai jisme ek component apni creation se lekar unmount hone tak kuch stages se guzarta hai. React mein component ka life cycle mainly 3 parts mein divide hota hai: Mounting, Updating, aur Unmounting.

## 1st Step:- Mounting (Component DOM mein insert ho raha hai)
Jab ek component pehli baar render hota hai, yaani jab wo DOM mein insert hota hai, to uske liye `Mounting` phase hota hai. Is phase mein kuch important methods call kiye jate hain:

#### constructor():
* Jab ek component create hota hai to constructor() sabse pehle call hota hai.
* Aap yahan initial state set kar sakte hain aur props ko initialize kar sakte hain.
* Agar aapko parent class ko constructor se call karna ho to super(props) likhna padta hai.


```python
constructor(props) {
  super(props);
  this.state = { count: 0 };
}
```

### static getDerivedStateFromProps():
* Ye method props change hone par state ko update karne ke liye use hota hai.
* Ye method render se pehle call hota hai, lekin yeh sirf class components mein hota hai.
* Agar props change hoti hain to aap state ko update kar sakte hain.


```python
static getDerivedStateFromProps(nextProps, nextState) {
  if (nextProps.value !== nextState.value) {
    return { value: nextProps.value };
  }
  return null;
}
```

### render():
* Ye method component ka actual UI render karta hai.
* React ki render method ek pure function hoti hai jo props aur state ke base par UI return karti hai.
* Ye method har time re-render hota hai jab state ya props change hoti hain.


```python
render() {
  return <div>{this.state.count}</div>;
}
```

### componentDidMount():
* Ye method component ke render hone ke baad call hota hai.
* Yahan aap side-effects (jaise API calls, event listeners, subscriptions, etc.) ko handle kar sakte hain.
* Agar aapko data fetch karna ho ya timer set karna ho to yeh method use hota hai.


```python
componentDidMount() {
  fetchData().then(data => this.setState({ data }));
}
```

# 2nd Step:- Updating (Component ka state ya props change ho raha hai)

Agar component ka state ya props change hota hai, to component re-render hota hai. Is process ko Updating kaha jata hai.

### static getDerivedStateFromProps():
* Jaise ki Mounting phase mein bataya gaya, yeh method props change hone par call hota hai aur state ko update karne ka kaam karta hai.

### shouldComponentUpdate():
* Ye method decide karta hai ki component ko re-render karna hai ya nahi. Agar yeh method false return karta hai, to component re-render nahi hoga.
* Ye method performance optimization ke liye use hota hai, jab aapko lagta hai ki props ya state change hone par re-render ki zarurat nahi hai.


```python
shouldComponentUpdate(nextProps, nextState) {
  if (nextState.count === this.state.count) {
    return false; // Re-render nahi hoga
  }
  return true; // Re-render hoga
}
```

### render():
* Jab component ka state ya props change hota hai, tab render() method call hota hai. Isme naya UI generate hota hai.

### getSnapshotBeforeUpdate():
* Ye method render() ke baad aur DOM update se pehle call hota hai.
* Agar aapko DOM ka snapshot lena ho ya scroll position ko track karna ho to yeh method use hota hai.


```python
getSnapshotBeforeUpdate(prevProps, prevState) {
  // Scroll position track karna
  return this.state.scrollPosition;
}
```

### componentDidUpdate():
* Ye method render() ke baad call hota hai, jab component successfully DOM mein update ho jata hai.
* Aap isme side effects ko handle kar sakte hain, jaise API call ya animations.


```python
componentDidUpdate(prevProps, prevState, snapshot) {
  if (this.state.count !== prevState.count) {
    // Data fetch ya kuch aur kar sakte hain
  }
}
```

# 3rd Step:- Unmounting (Component DOM se remove ho raha hai)

Jab ek component DOM se remove hota hai, to uske liye Unmounting phase hota hai.

### componentWillUnmount():
* Ye method component ke unmount hone se pehle call hota hai.
* Is method mein aapko cleanup tasks handle karne chahiye, jaise event listeners ko remove karna, timers ko clear karna, ya API requests ko cancel karna.


```python
componentWillUnmount() {
  clearInterval(this.timer);
}
```

React ka component life cycle aapko yeh samajhne mein madad karta hai ki component kab aur kaise update hota hai, aur jab wo unmount hota hai to uske cleanup tasks kya honge. Life cycle methods ko efficiently use karne se aap apne components ko optimized aur responsive bana sakte hain.

# Link & NavLink me Diff(React-Router-Dom)

## Link:-
Link component ka basic purpose hai ek route par navigate karna bina page ko reload kiye.

* Usage: Link simple navigation ke liye use hota hai.
* Behavior: Jab user Link par click karta hai, toh wo specified route pe navigate ho jaata hai.


```python
import { Link } from 'react-router-dom';

function App() {
  return (
    <nav>
      <Link to="/home">Home</Link>
      <Link to="/about">About</Link>
    </nav>
  );
}
```

## NavLink:
NavLink bhi Link ki tarah hi route navigation ka kaam karta hai, lekin isme ek extra feature hota hai: active class ka automatic management.
* Usage: NavLink ko zyada tar navigation links mein use kiya jata hai, jahan aapko current active link ko highlight karna hota hai (e.g., jab user currently ek page pe ho, toh uska link active dikhe).
* Behavior: Jab user NavLink par click karta hai, wo route ko navigate karta hai, aur agar wo current route ke saath match karta hai, toh active class automatically add hoti hai.


```python
import { NavLink } from 'react-router-dom';

function App() {
  return (
    <nav>
      <NavLink to="/home" activeClassName="active-link">Home</NavLink>
      <NavLink to="/about" activeClassName="active-link">About</NavLink>
    </nav>
  );
}
```

`Link: Simple navigation ke liye use hota hai, koi active state handling nahi hoti.`

`NavLink: Active navigation link ko highlight karne ke liye use hota hai, jisme automatic active class add hoti hai jab link current route ke saath match karta hai.`

# Redirect & Navigate:-

React Router DOM 6 (or later) me Redirect component ko replace kar diya gaya hai Navigate component se. Agar aapko ek route se dusre route par navigate karna hai, toh ab aap Navigate ka use kar sakte hain.


```python
import { Navigate } from 'react-router-dom';

function MyComponent() {
  // Some logic here
  return <Navigate to="/new-path" />;
}
```

* to prop: Yeh prop redirect hone wale route ko specify karta hai.
* replace prop: Agar replace={true} set karenge to current entry ko history stack mein replace kar diya jayega, matlab back button se wapas nahi ja sakte.

##### Agar aapko kisi route par ek element render karna ho, to aap Route component ka use karenge. Navigate sirf redirect ke liye hota hai, aur wo kisi component ko render nahi karta.

###  Key Differences:
#### Router:

v5 me: BrowserRouter ya HashRouter ko use karte the, jo specific routing mode decide karte the (browser history ya hash-based).

v6 me: Same tarike se BrowserRouter ya HashRouter use hota hai, lekin zyada tar cases me Routes component ki zarurat hoti hai.

#### Routes:

v5 me: Multiple Route components ko directly Router ke andar rakhte the.

v6 me: Route components ko Routes ke andar wrap karna padta hai, jisse wo route matching ka kaam efficiently perform karte hain.

#### Route:

v5 me: Route me component prop use hota tha, ya phir render ya children prop ka use hota tha.

v6 me: Route me element prop use hota hai, jisme ek React element pass karte hain.

# React Redux

React Redux ek JavaScript library hai jo React applications me state management ko asaan banata hai. Redux ek predictable state container hai jo apne app ke state ko ek centralized store me rakhta hai, jahan se har component apni required data ko fetch kar sakta hai.

Iska use state ko manage karne ke liye kiya jata hai, khaas kar jab aapko large scale applications me multiple components ke beech data share karna ho.

#### React Redux kaam kaise karta hai:

##### Store: 
Redux me ek central store hota hai jahan aap app ka state rakhte ho. Yeh state poore app ke liye accessible hota hai.

##### Actions: 
Actions ek plain JavaScript objects hote hain jo state me changes ke liye request bhejte hain. Action ek type field rakhta hai jo batata hai ki kis type ka action perform karna hai (jaise data fetch karna, user login, etc.).

##### Reducers: 
Reducers wo functions hote hain jo action ke basis par state ko modify karte hain. Jab action dispatch hota hai, reducer wo action handle karke updated state return karta hai.

##### Dispatch: 
React components me dispatch method use karke action ko call kiya jata hai, jise store me send kiya jata hai.

##### Connect: 
connect() function ka use kar ke React component ko Redux store se connect kiya jata hai. Iske zariye, component ko store se data milta hai aur state me changes reflect hoti hain.

### Redux ka fayda:
Single Source of Truth: Saare state ek jagah par rehte hain, jo debugging aur maintenance ko asaan banata hai.

Predictable: State ko modify karne ka process predictable hota hai, jise aap track kar sakte ho.

Easy Debugging: Aap actions aur state changes ko easily track kar sakte ho, jo development aur debugging me madadgar hai.

# What is Key?

React me "key" ek special prop hota hai jo list items ko uniquely identify karne ke liye use hota hai. Jab aap kisi list ko render karte ho (jaise map() method se), toh React ko pata hona chahiye ki kaunsa item update hua hai, kaunsa item delete hua hai, ya kaunsa item add hua hai. Isliye key ka use kiya jata hai.

React me key ka main purpose performance optimization aur re-rendering ko efficient banana hota hai.


```python
const items = ['Apple', 'Banana', 'Orange'];

const ItemList = () => {
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
};
```

#### Key ka Importance:
Jab aap React me list items render karte hain (jaise map() function se), toh React ko yeh samajhna hota hai ki har item ka unique identity kya hai, taki wo efficiently update kar sake jab state ya props change ho. Agar aap key ka sahi tareeke se use nahi karte, toh React ko har item ko re-render karna padta hai, jo unnecessary performance cost hota hai.

Agar aap key nahi provide karte, toh React default behavior me index ko key samajh kar use karta hai. Lekin yeh problem create kar sakta hai agar aapki list me items ka order change ho, ya items add/remove ho.

#### Key aur Re-rendering:
React ko jab list me changes dekhna hote hain (jaise item add ya remove ho), toh wo virtual DOM me check karta hai ki kis item ka position change hua hai. Agar key sahi se set ki gayi ho, toh React ko pata chal jata hai ki kis item ko update karna hai, bina poore list ko dobara render kiye. Isse rendering fast hota hai.


```python
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

# setState()

setState() React me ek method hai jo component ki state ko update karta hai. Lekin, jab hum functional components ki baat karte hain, to setState() ko directly use nahi kar sakte. Instead, functional components me hum useState() hook ka use karte hain, jo state ko handle karta hai.

useState() hook ko call karte waqt, hum ek initial state value set karte hain aur ek function milta hai jise hum state ko update karne ke liye use karte hain.


```python
import React, { useState } from 'react';

const Counter = () => {
  // State ko initialize karna (initial value 0 hai)
  const [count, setCount] = useState(0);

  // Function jo state ko update karega
  const increment = () => {
    setCount(count + 1);  // State ko update karna
  };

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={increment}>Increment</button>
    </div>
  );
};

export default Counter;
```

#### Explanation:
* const [count, setCount] = useState(0);
* count state variable hai jo initial value 0 se start hota hai.
* setCount wo function hai jo hum state ko update karne ke liye use karte hain.
* increment function ke andar, hum setCount(count + 1) call karte hain, jo count ki value ko 1 se increment karta hai.
* Jab button pe click hota hai, increment function call hota hai aur state update ho jati hai, jisse component re-render hota hai aur updated value UI me show hoti hai.

# Optimize React Code:-
* Use useCallback and useMemo Hooks
* Avoid Reconciliation with React.memo
* Lazy Load Components using React.lazy
* Use PureComponent or shouldComponentUpdate
* Avoid Inline Functions in JSX
* Batch State Updates
* Code Splitting
* Virtualize Long Lists
* Avoid Excessive Re-Renders
* Optimize CSS and Styling
* Consider Server-Side Rendering (SSR) 


# Strict Mode in React

React mein Strict Mode ek development tool hai jo aapke application ko check karta hai aur kuch common mistakes ya problematic patterns ko identify karta hai. Ye sirf development mode mein kaam karta hai aur production build mein effect nahi dalta.

#### Detecting Unsafe Lifecycles: 
React aapko un lifecycle methods ki warning deta hai jo future versions mein deprecated ho sakte hain. Jaise ki componentWillMount, componentWillReceiveProps, aur componentWillUpdate.

#### Identifying Components with Side Effects: 
Ye ensure karta hai ki components mein unnecessary side effects na ho. React aise components ko identify karta hai jo render ke dauran state ya props ko change karte hain.

#### Legacy Context API: 
Agar aap purani context API use kar rahe hain, toh Strict Mode aapko warn karega. React ne ek nayi context API introduce ki hai, jo ki zyada efficient hai.

#### Double Rendering: 
Strict Mode development mein components ko intentionally do baar render karta hai (double rendering) taaki aap easily identify kar sakein agar koi unexpected side effects ya issues ho rahe hain.


```python
import React from 'react';
import ReactDOM from 'react-dom';
import App from './App';

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```
