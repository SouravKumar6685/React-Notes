# 🎭 React Props & Children – Passing Data Like a Pro!

## 📖 **Story Time – The Magic Parcel 📦**
Imagine you own a **pizza shop** 🍕, and customers place orders. The chef **(Parent Component)** prepares the pizza and hands it over to the **delivery boy (Props)**, who then delivers it to the **customer (Child Component)**. 

**Props in React work the same way!** They help pass data from **parent components** to **child components** just like a parcel. 🎁

---

## 🧐 **What are Props in React?**
- **Props (short for Properties)** are used to **pass data** from one component to another.
- Props **are read-only (immutable)**, meaning a child component **cannot modify** the received props.
- They make components **reusable** and **dynamic**!

---

## 📂 **Folder Structure for Props & Children**
We organize our props-related files like this:

```
my-app/
│-- src/
│   │-- components/
│   │   │-- Greeting.jsx  # 🏷️ Child Component receiving props
│   │   │-- Wrapper.jsx   # 🏷️ Component using children props
│   │-- App.js  # 🔥 Parent Component passing props
│   │-- index.js  # 🚀 Entry Point
```

---

## 📝 **Code Explanation – Using Props**
### 🔹 **Step 1: Create a Child Component**
📄 `src/components/Greeting.jsx`
```jsx
import React from 'react';

function Greeting(props) {
  return <h2>Hello, {props.name}! 👋</h2>;
}

export default Greeting;
```
✅ **What’s happening?**
- We define a **functional component** `Greeting`.
- It receives `props` as an **argument** and uses `{props.name}` inside JSX.

---

### 🔹 **Step 2: Pass Props from Parent Component**
📄 `src/App.jsx`
```jsx
import React from 'react';
import Greeting from './components/Greeting';

function App() {
  return (
    <>
      <h1>Welcome to React Props 🚀</h1>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
    </>
  );
}

export default App;
```
✅ **What’s happening?**
- The **`App` component (parent)** passes different `name` values as props to `Greeting`.
- The **child component (`Greeting`)** receives the props and displays them dynamically.

---

## 🎭 **Props with Multiple Values**
Props can pass **multiple values** using an object.

📄 `src/components/UserInfo.jsx`
```jsx
import React from 'react';

function UserInfo(props) {
  return (
    <div>
      <h2>Name: {props.name}</h2>
      <p>Age: {props.age}</p>
      <p>Location: {props.location}</p>
    </div>
  );
}

export default UserInfo;
```

📄 `src/App.jsx`
```jsx
import React from 'react';
import UserInfo from './components/UserInfo';

function App() {
  return (
    <>
      <h1>User Details 🔍</h1>
      <UserInfo name="Charlie" age={25} location="India" />
    </>
  );
}

export default App;
```
✅ Here, **multiple props** (`name`, `age`, `location`) are passed and dynamically displayed!

---

## 🏆 **Using `children` Prop**
Sometimes we don’t pass just data but **entire components or elements** inside another component. This is where **`children` prop** comes in!

📄 `src/components/Wrapper.jsx`
```jsx
import React from 'react';

function Wrapper(props) {
  return (
    <div style={{ border: '2px solid black', padding: '10px', margin: '10px' }}>
      {props.children}
    </div>
  );
}

export default Wrapper;
```
✅ **What’s happening?**
- The `Wrapper` component **does not have predefined content**.
- It simply **wraps** whatever is inside it using `{props.children}`.

### **Using `children` in Parent Component**
📄 `src/App.jsx`
```jsx
import React from 'react';
import Wrapper from './components/Wrapper';

function App() {
  return (
    <>
      <h1>Using Children Prop 👶</h1>
      <Wrapper>
        <p>This is wrapped inside a custom component!</p>
      </Wrapper>
    </>
  );
}

export default App;
```

✅ **Expected Output:**
```
Using Children Prop 👶
----------------------------
| This is wrapped inside a custom component! |
----------------------------
```
Now, whatever is placed inside `<Wrapper>` will be passed as `props.children` and displayed!

---

## 🏆 **Key Points About Props & Children**
✔ **Props are immutable** – Cannot be modified inside the child component.
✔ **Props allow reusability** – The same component can be used with different values.
✔ **Props make components dynamic** – Instead of hardcoding values, they can be passed.
✔ **Props can be objects, arrays, functions, or components** – Not just strings & numbers!
✔ **`children` prop allows wrapping content inside another component**.

---

## 🚀 **Advanced: Destructuring Props**
Instead of using `props.name`, `props.age`, etc., we can **destructure** props like this:

📄 `src/components/UserCard.jsx`
```jsx
import React from 'react';

function UserCard({ name, age, location }) {
  return (
    <div>
      <h2>{name}</h2>
      <p>Age: {age}</p>
      <p>Location: {location}</p>
    </div>
  );
}

export default UserCard;
```

Now we don’t need `props.` before every variable. Much cleaner! 🚀

---

## 🎯 **Final Takeaways**
✅ **Props help pass data** from parent to child components.
✅ **They are immutable** (cannot be changed in child components).
✅ **Multiple props** can be passed (strings, numbers, objects, functions, etc.).
✅ **Destructuring makes props cleaner**.
✅ **`children` prop allows component composition**.

Now you’re a **Props & Children Pro**! 🎉 Next, let’s explore more React concepts! 🚀

