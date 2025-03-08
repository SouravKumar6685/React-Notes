# 🌍 React Context – The Power of Global State Management 🚀

## 📖 **Story Time – The Lost Parcel 📦**
Imagine you are in a **huge office building** 🏢 with **100 floors**. You are on the 100th floor and need an important parcel 📦 that is currently on the **ground floor**.

In a normal scenario, you'd have to go floor by floor, asking each person to **pass the parcel** upwards. This is like **prop drilling** in React, where every component passes data to its child, even if only the last component needs it! 😩

But what if there was a **central messaging system** 📢 where you could **directly access** the parcel from any floor? That's exactly what **React Context** does! 🎉

---

## 🧐 **What is React Context?**
- React Context provides a way to **share data globally** without **prop drilling** (passing props through multiple levels of components).
- Used for managing **theme settings 🎨, user authentication 👤, language preferences 🌍, and more**.
- Works like a **global storage** that any component can access **without explicitly passing props**.

---

## 📂 **Folder Structure for Context API Example**
```
my-app/
│-- src/
│   │-- context/
│   │   │-- ThemeContext.jsx  # 🎨 Theme context
│   │   │-- UserContext.jsx  # 👤 User authentication context
│   │-- components/
│   │   │-- Navbar.jsx  # 🔝 Uses context to get theme
│   │   │-- Profile.jsx  # 👤 Uses context to get user info
│   │-- App.jsx  # 🚀 Parent Component
│   │-- index.jsx  # 🏁 Entry Point
```

---

## 📝 **How to Use React Context – Examples & Explanation**

### 1️⃣ **Creating a Context – Theme Example 🎨**
📄 `src/context/ThemeContext.jsx`
```jsx
import React, { createContext, useState } from 'react';

// 1️⃣ Create Context
export const ThemeContext = createContext();

export function ThemeProvider({ children }) {
  const [theme, setTheme] = useState("light");

  const toggleTheme = () => {
    setTheme(prevTheme => (prevTheme === "light" ? "dark" : "light"));
  };

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}
```
✅ **Here, we create a `ThemeContext` and provide a way to toggle between light and dark themes.**

---

### 2️⃣ **Using Context in a Component – Navbar Example 🔝**
📄 `src/components/Navbar.jsx`
```jsx
import React, { useContext } from 'react';
import { ThemeContext } from '../context/ThemeContext';

function Navbar() {
  const { theme, toggleTheme } = useContext(ThemeContext); // 🎯 Using context

  return (
    <nav style={{ background: theme === "light" ? "#fff" : "#333", color: theme === "light" ? "#000" : "#fff" }}>
      <h2>🌍 Theme: {theme}</h2>
      <button onClick={toggleTheme}>Toggle Theme</button>
    </nav>
  );
}

export default Navbar;
```
✅ **Now, the `Navbar` component can access the `theme` and `toggleTheme` function without prop drilling!**

---

### 3️⃣ **Wrapping the App with Context Provider 🌍**
📄 `src/App.jsx`
```jsx
import React from 'react';
import { ThemeProvider } from './context/ThemeContext';
import Navbar from './components/Navbar';

function App() {
  return (
    <ThemeProvider> {/* 🌍 Wrapping the entire app with ThemeProvider */}
      <Navbar />
    </ThemeProvider>
  );
}

export default App;
```
✅ **Here, we wrap the entire app inside `ThemeProvider` so that `Navbar` can access the context.**

---

### 4️⃣ **Another Example – User Authentication Context 👤**
📄 `src/context/UserContext.jsx`
```jsx
import React, { createContext, useState } from 'react';

export const UserContext = createContext();

export function UserProvider({ children }) {
  const [user, setUser] = useState(null);

  return (
    <UserContext.Provider value={{ user, setUser }}>
      {children}
    </UserContext.Provider>
  );
}
```
📄 `src/components/Profile.jsx`
```jsx
import React, { useContext } from 'react';
import { UserContext } from '../context/UserContext';

function Profile() {
  const { user, setUser } = useContext(UserContext);

  return (
    <div>
      <h2>👤 {user ? `Welcome, ${user.name}!` : "Please log in."}</h2>
      <button onClick={() => setUser({ name: "John Doe" })}>Login</button>
    </div>
  );
}

export default Profile;
```
✅ **Now, `Profile` component can access and update user information globally without passing props.**

---

## 🎯 **Best Practices for Using Context**
✅ Use Context for **global state management** like **themes, authentication, and language settings**.
✅ Wrap the **entire application** inside the `Provider` to make data accessible everywhere.
✅ Use **multiple contexts** if needed (e.g., `ThemeContext` and `UserContext`).
✅ Use `useReducer` with Context for **complex state management** instead of just `useState`.

---

## 🚀 **Final Takeaways**
✅ **React Context provides a way to manage global state** without prop drilling. 🔥
✅ **Works great for themes, authentication, and global settings**. 🎨
✅ **Using `useContext()` allows direct access to the stored data**. 🏆

🎉 Now you understand **React Context**! Ready for the next topic? 🚀

