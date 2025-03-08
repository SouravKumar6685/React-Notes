# 🔥 React Hooks – The Power of Functional Components 🚀

## 📖 **Story Time – The Magic of Hooks ✨**
Imagine you are building a React app, and you need to:
- Store user data ✅
- Fetch API data when a component loads ✅
- Respond to user interactions ✅

Before React **Hooks**, developers had to use **class components** for managing state and lifecycle methods. But now, with **Hooks**, functional components can do all of this easily! 🎉

---

## 🧐 **What Are React Hooks?**
Hooks **allow functional components** to use state and lifecycle methods **without writing a class**. They make React components **simpler, reusable, and powerful**. 🔥

### ✅ **Why Use Hooks?**
- No need for **class components** 🚫
- Makes components **cleaner & readable** ✅
- Encourages **reusability & modular code** 🔄
- Enables **state management inside functional components** 🔥

---

## 📂 **Folder Structure for Hooks Example**
```
my-app/
│-- src/
│   │-- components/
│   │   │-- Counter.jsx  # 📝 useState Example
│   │   │-- Timer.jsx  # ⏳ useEffect Example
│   │-- App.jsx  # 🔥 Parent Component
│   │-- index.jsx  # 🚀 Entry Point
```

---

## 📝 **Essential React Hooks (with Examples)**
### 1️⃣ **useState – Managing State in Functional Components**
`useState` allows functional components to have state variables.

📄 `src/components/Counter.jsx`
```jsx
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>Counter: {count}</h2>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}

export default Counter;
```
✅ **What’s happening?**
- `useState(0)` initializes `count` to **0**.
- `setCount(count + 1)` updates the state.
- React **re-renders** the component when state changes.

---

### 2️⃣ **useEffect – Handling Side Effects (API Calls, Timers, etc.)**
`useEffect` allows us to run code **after the component renders**.

📄 `src/components/Timer.jsx`
```jsx
import React, { useState, useEffect } from 'react';

function Timer() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    const interval = setInterval(() => {
      setSeconds((prev) => prev + 1);
    }, 1000);
    
    return () => clearInterval(interval); // Cleanup on unmount
  }, []);

  return <h2>Timer: {seconds} seconds</h2>;
}

export default Timer;
```
✅ **What’s happening?**
- `useEffect` runs **after the component mounts**.
- **Updates the timer every second**.
- `return () => clearInterval(interval);` cleans up the effect when the component **unmounts**.

---

### 3️⃣ **useContext – Global State Management**
Instead of **prop drilling**, we use `useContext` to share data across components.

📄 `src/context/ThemeContext.jsx`
```jsx
import React, { createContext, useState } from 'react';

const ThemeContext = createContext();

export function ThemeProvider({ children }) {
  const [theme, setTheme] = useState("light");
  
  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}

export default ThemeContext;
```
📄 `src/App.jsx`
```jsx
import React, { useContext } from 'react';
import ThemeContext, { ThemeProvider } from './context/ThemeContext';

function ThemeToggle() {
  const { theme, setTheme } = useContext(ThemeContext);
  return (
    <button onClick={() => setTheme(theme === "light" ? "dark" : "light")}>
      Toggle Theme (Current: {theme})
    </button>
  );
}

export default function App() {
  return (
    <ThemeProvider>
      <h1>React useContext Example</h1>
      <ThemeToggle />
    </ThemeProvider>
  );
}
```
✅ **What’s happening?**
- `useContext(ThemeContext)` gives access to `theme` and `setTheme`.
- Clicking the button **toggles the theme** globally.

---

## 🚀 **More Advanced Hooks**
### 🔹 **useRef – Accessing DOM Elements**
```jsx
const inputRef = useRef(null);
<input ref={inputRef} />
```
✅ `useRef` gives **direct access** to a DOM element.

### 🔹 **useReducer – Advanced State Management**
```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```
✅ `useReducer` is like **Redux** but simpler for local state management.

---

## 🎯 **Final Takeaways**
✅ React Hooks **remove the need for class components** 🚫
✅ `useState` manages **local state** 📊
✅ `useEffect` handles **side effects** like API calls & timers ⏳
✅ `useContext` simplifies **state sharing** across components 🔄
✅ Advanced hooks like `useRef` and `useReducer` help in complex scenarios ⚡

🔥 Now you’re a **React Hooks Master**! Ready for the next topic? 🚀

