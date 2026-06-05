# useRef Hook

## Introduction

`useRef` React ka ek Hook hai jo kisi **DOM Element** ya **Value** ka reference store karne ke liye use hota hai.

Sabse important baat:

> `useRef` ki value change hone par component re-render nahi hota.

Isi wajah se `useRef` aur `useState` me kaafi difference hai.

---

# Syntax

```jsx
const myRef = useRef(initialValue);
```

Example:

```jsx
const countRef = useRef(0);
```

Output:

```javascript
{
    current: 0
}
```

React internally ek object create karta hai:

```javascript
{
    current: initialValue
}
```

---

# useRef Kaise Kaam Karta Hai?

```jsx
const countRef = useRef(0);

console.log(countRef.current);
```

Output:

```text
0
```

Value update:

```jsx
countRef.current = 10;
```

Output:

```text
10
```

Lekin UI update nahi hogi kyunki re-render nahi hota.

---

# Example 1 : DOM Access

Sabse common use case.

```jsx
import { useRef } from "react";

function App() {

    const inputRef = useRef();

    const focusInput = () => {
        inputRef.current.focus();
    };

    return (
        <>
            <input ref={inputRef} />

            <button onClick={focusInput}>
                Focus
            </button>
        </>
    );
}

export default App;
```

## Kaise Kaam Karta Hai?

### Step 1

```jsx
const inputRef = useRef();
```

React ek ref object banata hai.

```javascript
{
    current: undefined
}
```

### Step 2

```jsx
<input ref={inputRef} />
```

Input render hote hi React actual DOM element ko `current` me store kar deta hai.

```javascript
{
    current: <input />
}
```

### Step 3

```jsx
inputRef.current.focus();
```

Input box focus ho jata hai.

---

# Example 2 : Value Store Karna

```jsx
import { useRef } from "react";

function App() {

    const countRef = useRef(0);

    const increment = () => {
        countRef.current++;
        console.log(countRef.current);
    };

    return (
        <button onClick={increment}>
            Increment
        </button>
    );
}
```

Output Console:

```text
1
2
3
4
```

UI change nahi hogi kyunki re-render nahi hua.

---

# Example 3 : useState vs useRef

## useState

```jsx
const [count, setCount] = useState(0);

setCount(count + 1);
```

Result:

```text
Component Re-render
UI Update
```

---

## useRef

```jsx
const countRef = useRef(0);

countRef.current++;
```

Result:

```text
No Re-render
No UI Update
```

---

# Real Example

## Count UI Update Karna

```jsx
const [count, setCount] = useState(0);
```

Use `useState`.

---

## Previous Value Store Karna

```jsx
const previousValue = useRef();
```

Use `useRef`.

---

## Input Focus Karna

```jsx
const inputRef = useRef();
```

Use `useRef`.

---

# useRef vs useState

| Feature | useRef | useState |
|----------|----------|----------|
| Re-render | ❌ No | ✅ Yes |
| DOM Access | ✅ Yes | ❌ No |
| Value Store | ✅ Yes | ✅ Yes |
| UI Update | ❌ No | ✅ Yes |
| Mutable Value | ✅ Yes | ❌ No |

---

# Important Points

### Ref Object

```jsx
const ref = useRef();
```

Output:

```javascript
{
    current: undefined
}
```

---

### Current Property

Value hamesha `current` me store hoti hai.

```jsx
ref.current
```

---

### Re-render Nahi Hota

```jsx
ref.current = 100;
```

React UI update nahi karega.

---

### DOM Access

```jsx
inputRef.current.focus();
```

```jsx
inputRef.current.value
```

```jsx
inputRef.current.style.color = "red";
```

Direct DOM access kar sakte hain.

---

# React 19

React 19 me `useRef` ka syntax aur behavior same hai.

```jsx
const myRef = useRef();
```

Koi major change nahi hua hai.

---

# Summary

- `useRef` DOM element ya value ka reference store karta hai.
- Value `current` property me store hoti hai.
- `useRef` value change hone par component re-render nahi hota.
- Input focus, DOM access aur previous values store karne ke liye commonly use hota hai.
- UI update karni ho to `useState` use karo.
- Re-render ke bina value store karni ho to `useRef` use karo.

# Controlled Component

## Introduction

Controlled Component wo component hota hai jisme form input ki value React ke State (`useState`) dwara control ki jati hai.

Simple words me:

> Input box me jo bhi value dikh rahi hoti hai, wo React State se aati hai.

Matlab React hi input ki value ko read bhi karta hai aur update bhi karta hai.

---

# Flow of Controlled Component

```text
User Input
    ↓
onChange Event
    ↓
State Update
    ↓
Component Re-render
    ↓
Updated Value UI Me Show
```

---

# Basic Example

```jsx
import { useState } from "react";

function App() {

    const [name, setName] = useState("");

    return (
        <input
            type="text"
            value={name}
            onChange={(e) => setName(e.target.value)}
        />
    );
}
```

---

# Is Example Ko Samjho

## Step 1: State Create Hui

```jsx
const [name, setName] = useState("");
```

Initial Value:

```text
name = ""
```

---

## Step 2: Input State Se Connected Hai

```jsx
value={name}
```

Matlab input ki value hamesha state se aayegi.

```text
Input Value = State Value
```

---

## Step 3: User Typing Karta Hai

User type karta hai:

```text
B
```

Input Event Trigger:

```jsx
onChange={(e) => setName(e.target.value)}
```

---

## Step 4: State Update Hoti Hai

```jsx
setName("B")
```

State:

```text
name = "B"
```

---

## Step 5: Component Re-render

React component dubara render karta hai.

```jsx
value={name}
```

Ab:

```text
value="B"
```

Input me "B" show ho jayega.

---

# Real Example

```jsx
import { useState } from "react";

function App() {

    const [name, setName] = useState("");

    return (
        <>
            <input
                type="text"
                value={name}
                onChange={(e) => setName(e.target.value)}
            />

            <h2>Name: {name}</h2>
        </>
    );
}
```

### Output

User type kare:

```text
Bittu
```

To screen par:

```text
Name: Bittu
```

Real-time update hoga.

---

# Controlled Kyu Kehte Hain?

Ye line dekho:

```jsx
value={name}
```

Input ki value user direct control nahi kar raha.

React State control kar rahi hai.

Isliye ise **Controlled Component** kehte hain.

---

# Validation Example

Controlled Components me validation bahut easy hoti hai.

```jsx
import { useState } from "react";

function App() {

    const [name, setName] = useState("");

    const handleChange = (e) => {

        const value = e.target.value;

        if (value.length <= 10) {
            setName(value);
        }
    };

    return (
        <input
            value={name}
            onChange={handleChange}
        />
    );
}
```

### Result

```text
10 Characters Se Jyada Type Nahi Kar Sakte
```

Ye sab easy hai kyunki React ke paas value ka control hai.

---

# Multiple Inputs Example

```jsx
import { useState } from "react";

function App() {

    const [formData, setFormData] = useState({
        name: "",
        email: ""
    });

    const handleChange = (e) => {
        setFormData({
            ...formData,
            [e.target.name]: e.target.value
        });
    };

    return (
        <>
            <input
                name="name"
                value={formData.name}
                onChange={handleChange}
            />

            <input
                name="email"
                value={formData.email}
                onChange={handleChange}
            />
        </>
    );
}
```

---

# Benefits

### Easy Validation

```jsx
if(value.length > 10)
```

---

### Real-Time UI Update

```jsx
<h1>{name}</h1>
```

---

### Easy Form Handling

```jsx
value={state}
```

---

### Single Source of Truth

Saara data React State me rehta hai.

---

# Controlled vs Uncontrolled

## Controlled

```jsx
<input
    value={name}
    onChange={(e) => setName(e.target.value)}
/>
```

Data Store:

```text
React State
```

---

## Uncontrolled

```jsx
<input ref={inputRef} />
```

Data Store:

```text
DOM
```

---

# Easy Trick

Ye line yaad rakho:

```jsx
value={state}
```

Agar input me `value` state se aa rahi hai aur `onChange` state update kar raha hai, to wo **Controlled Component** hai.

```jsx
<input
    value={name}
    onChange={(e) => setName(e.target.value)}
/>
```

---

# Summary

- Controlled Component me input React State se control hota hai.
- `useState` ka use kiya jata hai.
- Input ki value `value` prop se bind hoti hai.
- User jab type karta hai to `onChange` state update karta hai.
- State update hone par component re-render hota hai.
- Validation aur form handling ke liye Controlled Components sabse zyada use hote hain.

# Uncontrolled Component

## Introduction

Uncontrolled Component wo component hota hai jisme form input ki value React State se control nahi hoti.

Isme input ki value **DOM (Document Object Model)** ke andar store rehti hai aur React us value ko directly manage nahi karta.

Generally value access karne ke liye `useRef` use kiya jata hai.

---

# Controlled vs Uncontrolled

### Controlled Component

```jsx
<input
    value={name}
    onChange={(e) => setName(e.target.value)}
/>
```

Data Store:

```text
React State
```

---

### Uncontrolled Component

```jsx
<input ref={inputRef} />
```

Data Store:

```text
DOM
```

---

# Basic Example

```jsx
import { useRef } from "react";

function App() {

    const inputRef = useRef();

    const getValue = () => {
        alert(inputRef.current.value);
    };

    return (
        <>
            <input
                type="text"
                ref={inputRef}
            />

            <button onClick={getValue}>
                Get Value
            </button>
        </>
    );
}
```

---

# Kaise Kaam Karta Hai?

## Step 1

Ref Create Karo

```jsx
const inputRef = useRef();
```

---

## Step 2

Ref Ko Input Se Connect Karo

```jsx
<input ref={inputRef} />
```

React input element ka reference `inputRef.current` me store kar deta hai.

---

## Step 3

Value Access Karo

```jsx
inputRef.current.value
```

Example:

```jsx
const getValue = () => {
    console.log(inputRef.current.value);
};
```

---

# Real Example

```jsx
import { useRef } from "react";

function App() {

    const nameRef = useRef();

    const handleSubmit = () => {
        alert(`Name: ${nameRef.current.value}`);
    };

    return (
        <>
            <input
                type="text"
                ref={nameRef}
            />

            <button onClick={handleSubmit}>
                Submit
            </button>
        </>
    );
}
```

### Output

User Type:

```text
Bittu
```

Button Click:

```text
Name: Bittu
```

---

# Why Use Uncontrolled Component?

Jab hume har keystroke par state update nahi karni ho.

Example:

- Search Box
- Simple Form
- Third Party Libraries Integration
- File Input

---

# File Input Example

File input mostly uncontrolled hota hai.

```jsx
import { useRef } from "react";

function App() {

    const fileRef = useRef();

    const handleFile = () => {
        console.log(fileRef.current.files[0]);
    };

    return (
        <>
            <input
                type="file"
                ref={fileRef}
            />

            <button onClick={handleFile}>
                Upload
            </button>
        </>
    );
}
```

---

# Benefits

### No Re-render

```text
Fast Performance
```

---

### Less Code

```jsx
<input ref={inputRef} />
```

---

### Easy DOM Access

```jsx
inputRef.current.value
```

---

# Drawbacks

### Validation Difficult

```text
Manual Validation Karni Padti Hai
```

---

### Real-Time Data Access Nahi

```text
Value Tabhi Milegi Jab Ref Se Read Karoge
```

---

### React Recommended Nahi

Complex Forms ke liye React mostly Controlled Components recommend karta hai.

---

# Easy Trick

Agar Input me:

```jsx
value={state}
onChange={...}
```

Hai ➜ **Controlled Component**

---

Agar Input me:

```jsx
ref={inputRef}
```

Hai ➜ **Uncontrolled Component**

---

# Summary

- Uncontrolled Component me input ki value DOM manage karta hai.
- React State use nahi hoti.
- `useRef` ka use karke value access karte hain.
- Input ki value `ref.current.value` se milti hai.
- Value change hone par component re-render nahi hota.
- File inputs aur simple forms me commonly use hota hai.

# Controlled Component vs Uncontrolled Component

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

## Controlled Component

```jsx
const [name, setName] = useState("");

<input
    value={name}
    onChange={(e) => setName(e.target.value)}
/>
```

### Data Flow

```text
Input → State → UI
```

---

## Uncontrolled Component

```jsx
const inputRef = useRef();

<input ref={inputRef} />

console.log(inputRef.current.value);
```

### Data Flow

```text
Input → DOM
```

---

## Easy Trick

### Controlled

```jsx
value={state}
onChange={...}
```

> React Input ko control kar raha hai.

---

### Uncontrolled

```jsx
ref={inputRef}
```

> DOM Input ko control kar raha hai.

# forwardRef

## Introduction

Normally `ref` ko direct HTML elements par lagaya jata hai.

```jsx
<input ref={inputRef} />
```

Lekin jab Parent Component ko Child Component ke andar kisi DOM element ka access chahiye ho, tab `forwardRef` use kiya jata hai.

> `forwardRef` Parent Component ki ref ko Child Component ke DOM element tak forward karta hai.

---

# Problem Without forwardRef

## Child Component

```jsx
function Input() {
    return <input />;
}
```

## Parent Component

```jsx
function App() {

    const inputRef = useRef();

    return <Input ref={inputRef} />;
}
```

❌ Error

```text
Function components cannot be given refs
```

Reason:

```text
Ref direct Functional Component par kaam nahi karti.
```

---

# Solution Using forwardRef

## Child Component

```jsx
import { forwardRef } from "react";

const Input = forwardRef((props, ref) => {
    return <input ref={ref} />;
});

export default Input;
```

---

## Parent Component

```jsx
import { useRef } from "react";
import Input from "./Input";

function App() {

    const inputRef = useRef();

    const focusInput = () => {
        inputRef.current.focus();
    };

    return (
        <>
            <Input ref={inputRef} />

            <button onClick={focusInput}>
                Focus
            </button>
        </>
    );
}
```

---

# Flow

```text
Parent Component
        ↓
      ref
        ↓
forwardRef
        ↓
Child Component
        ↓
<input />
```

---

# Real Example

## Child.jsx

```jsx
import { forwardRef } from "react";

const Child = forwardRef((props, ref) => {
    return <input ref={ref} />;
});

export default Child;
```

---

## App.jsx

```jsx
import { useRef } from "react";
import Child from "./Child";

function App() {

    const inputRef = useRef();

    return (
        <>
            <Child ref={inputRef} />

            <button
                onClick={() => inputRef.current.focus()}
            >
                Focus Input
            </button>
        </>
    );
}
```

---

# Why Use forwardRef?

### Parent Se Child DOM Access

```jsx
inputRef.current.focus();
```

---

### Input Focus Karna

```jsx
inputRef.current.focus();
```

---

### Scroll Karna

```jsx
ref.current.scrollIntoView();
```

---

### Third Party Libraries

DOM access ki zarurat ho to.

---

# React 19 Note

React 19 me `forwardRef` ab bhi supported hai.

Lekin React 19 me `ref` ko normal prop ki tarah pass karne ki capability introduce ki gayi hai, isliye future me kai cases me `forwardRef` ki zarurat kam ho sakti hai.

Phir bhi existing projects aur interviews me `forwardRef` ka concept bahut important hai.

---

# Summary

- `forwardRef` Parent ki ref ko Child Component ke DOM element tak pahunchata hai.
- Functional Components par direct ref kaam nahi karti.
- `forwardRef` is problem ko solve karta hai.
- Common use cases:
  - Input Focus
  - Scroll
  - DOM Access
  - Third Party Library Integration

## Introduction

`useFormStatus` React 19 ka ek Hook hai jo form ke current submission status ko track karne ke liye use hota hai.

Jab user form submit karta hai, tab hume aksar ye janana hota hai ki:

- Form submit ho raha hai ya nahi?
- API response ka wait chal raha hai ya nahi?
- Submit button disable karna hai ya nahi?
- Loading message dikhana hai ya nahi?

In sab cheezon ko handle karne ke liye React 19 me `useFormStatus` introduce kiya gaya hai.

---

### Problem Before useFormStatus

React 18 ya usse pehle hume loading state manually manage karni padti thi.

```jsx
const [loading, setLoading] = useState(false);
```

```jsx
const handleSubmit = async () => {
    setLoading(true);

    await saveData();

    setLoading(false);
};
```

Har form me alag state banani padti thi.

---

### Solution: useFormStatus

React 19 me `useFormStatus` automatically form ka status provide karta hai.

```jsx
const { pending } = useFormStatus();
```

### pending = false

```text
Form submit nahi ho raha hai
```

### pending = true

```text
Form submit ho raha hai
```

---

### Real-Life Example

Maan lo user registration form fill karta hai.

```text
Name: Bittu
Email: bittu@gmail.com
```

User Submit button par click karta hai.

Us time:

```text
Data Server Par Ja Raha Hai
```

Agar server response aane me 3 second lagte hain to:

```text
pending = true
```

Hum button ko disable kar sakte hain:

```jsx
<button disabled={pending}>
    {pending ? "Submitting..." : "Submit"}
</button>
```

Output:

```text
Submitting...
```

Server response aate hi:

```text
pending = false
```

Button phir normal ho jayega:

```text
Submit
```

---

### Easy Definition

> `useFormStatus` ek React 19 Hook hai jo form submit hone ke dauran uska current status (pending state) batata hai, jisse loading indicators, disabled buttons aur better user experience implement kiya ja sakta hai.

# useTransition Hook

## Introduction

`useTransition` React ka Hook hai jo non-urgent (low priority) updates ko handle karne ke liye use hota hai.

Simple words me:

> Kuch updates important hote hain (jaise typing) aur kuch updates less important hote hain (jaise large list render karna). `useTransition` React ko batata hai ki kaun se updates low priority hain.

Isse UI freeze nahi hoti aur application smooth rehti hai.

---

# Why useTransition?

Maan lo user search box me type kar raha hai aur har character par 10,000 records filter ho rahe hain.

Without `useTransition`:

```text
Typing Slow Ho Sakti Hai
UI Lag Kar Sakti Hai
```

With `useTransition`:

```text
Typing Fast Rahegi
Heavy Rendering Background Me Hogi
```

---

# Syntax

```jsx
const [isPending, startTransition] = useTransition();
```

---

# Return Values

| Value | Description |
|---------|---------|
| `isPending` | Transition chal raha hai ya nahi |
| `startTransition()` | Low Priority Update Start karta hai |

---

# Basic Example

```jsx
import { useState, useTransition } from "react";

function App() {

    const [text, setText] = useState("");
    const [list, setList] = useState([]);

    const handleChange = (e) => {

        const value = e.target.value;

        setText(value);

        startTransition(() => {

            const items = [];

            for (let i = 0; i < 5000; i++) {
                items.push(value);
            }

            setList(items);
        });
    };

    const [isPending, startTransition] = useTransition();

    return (
        <>
            <input
                type="text"
                value={text}
                onChange={handleChange}
            />

            {isPending && <p>Loading...</p>}

            {list.map((item, index) => (
                <p key={index}>{item}</p>
            ))}
        </>
    );
}
```

---

# Kaise Kaam Karta Hai?

### High Priority Update

```jsx
setText(value);
```

Ye immediately execute hoga.

---

### Low Priority Update

```jsx
startTransition(() => {
    setList(items);
});
```

Ye background me execute hoga.

---

# isPending

```jsx
const [isPending, startTransition] = useTransition();
```

Agar transition chal raha hai:

```text
isPending = true
```

Nahi chal raha:

```text
isPending = false
```

Example:

```jsx
{
    isPending && <p>Loading...</p>
}
```

---

# Real Life Example

### Search Filter

```text
User Typing
↓
Search Result Filter
↓
10000 Records Render
```

`useTransition` typing ko smooth rakhta hai.

---

### Dashboard

```text
Button Click
↓
Heavy Data Load
↓
Charts Render
```

Heavy updates ko transition me daal sakte hain.

---

# Without useTransition

```jsx
setText(value);
setList(bigData);
```

Result:

```text
UI Slow Ho Sakti Hai
```

---

# With useTransition

```jsx
setText(value);

startTransition(() => {
    setList(bigData);
});
```

Result:

```text
UI Responsive Rahegi
```

---

# Important Points

- React 18 me introduce hua tha.
- React 19 me bhi available hai.
- Heavy UI updates ke liye use hota hai.
- User interactions ko smooth banata hai.
- Performance improve karne me help karta hai.

---

# Summary

- `useTransition` low priority updates ko handle karta hai.
- `startTransition()` ke andar heavy updates likhte hain.
- `isPending` se loading state check kar sakte hain.
- UI ko responsive aur smooth banata hai.
- Search, filtering aur large list rendering me bahut useful hai.

# React Component Life Cycle क्या होती है?

Component Life Cycle का मतलब है एक कंपोनेंट का जन्म होने (DOM में आने) से लेकर उसके खत्म होने (DOM से हटने) तक का पूरा सफर। इसके 3 मुख्य स्टेज (Phases) होते हैं:

## 1. Mounting (पैदा होना / DOM में आना)
- जब कंपोनेंट पहली बार स्क्रीन पर लोड (रेंडर) होता है।

- Hooks में उपयोग: useEffect के साथ खाली डिपेंडेंसी एरे [] लगाते हैं ताकि यह कोड सिर्फ एक बार चले (जैसे API से डेटा लाना)।

```jsx
useEffect(() => {
  console.log("Component लोड हो गया! (Mounting)");
}, []);
```

## 2. Updating (बदलाव आना / Re-render होना)
- जब कंपोनेंट के लोड होने के बाद उसका कोई State या Props बदलता है, तो कंपोनेंट फिर से रेंडर होता है।

- Hooks में उपयोग: useEffect के डिपेंडेंसी एरे में उस वेरिएबल का नाम डालते हैं जिसके बदलने पर कोड चलाना हो।

```jsx
useEffect(() => {
  console.log("State या Prop बदल गया! (Updating)");
}, [count]); // count बदलने पर चलेगा
```

## 3. Unmounting (खत्म होना / DOM से हटना)
- जब कंपोनेंट स्क्रीन से गायब हो जाता है या डिलीट हो जाता है (जैसे पेज बदलने पर)।

- Hooks में उपयोग: useEffect के अंदर से एक Cleanup Function रिटर्न (return) किया जाता है जो मेमोरी क्लियर करने या टाइमर बंद करने के काम आता है।

```jsx
useEffect(() => {
  return () => {
    console.log("Component स्क्रीन से हट गया! (Unmounting)");
  };
}, []);
```
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