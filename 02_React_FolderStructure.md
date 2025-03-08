# React Folder Structure Guide

## 📂 Standard React Project Structure
When you create a new React app using `create-react-app`, you get a predefined folder structure:

```
my-app/
│-- node_modules/   # 📦 Dependencies installed by npm/yarn
│-- public/         # 🌐 Static assets (index.html, icons, etc.)
│   │-- index.html  # 🔥 Main HTML file where React app is injected
│   │-- favicon.ico # 🎨 App icon
│   └── manifest.json # 📜 PWA settings
│-- src/            # 🎯 Main source code of your React app
│   │-- components/  # 📂 Reusable UI components
│   │-- pages/       # 📂 Page-based components (for routing)
│   │-- assets/      # 🖼️ Static assets like images, styles
│   │-- hooks/       # 🔄 Custom React hooks
│   │-- context/     # 📌 Global state management using Context API
│   │-- App.js       # 🏠 Root component of your application
│   │-- index.js     # 🚀 Entry point of your app
│   └── styles.css   # 🎨 Global styles
│-- .gitignore       # 🚫 Files & folders to ignore in Git
│-- package.json     # 📜 Project dependencies & scripts
│-- README.md        # 📖 Project documentation
```

---

## 📂 Explanation of Key Folders

### 1️⃣ `node_modules/`
- Contains all installed dependencies.
- Auto-generated when you run `npm install` or `yarn install`.
- **❌ Do not edit manually!**

### 2️⃣ `public/`
- Stores static files like `index.html`, icons, and PWA settings.
- `index.html` is the entry point where React is injected.
- **React does not process files inside `public/` (except index.html).**

### 3️⃣ `src/`
- **The main folder where React code resides.**
- Contains components, pages, hooks, assets, and context.

#### 📁 `components/`
- Stores **reusable UI elements** (e.g., buttons, modals, forms).
- Example:
  ```jsx
  // src/components/Button.js
  export default function Button({ text }) {
    return <button>{text}</button>;
  }
  ```

#### 📁 `pages/`
- Organizes different pages for **React Router**.
- Example:
  ```jsx
  // src/pages/Home.js
  export default function Home() {
    return <h1>Welcome to Home Page</h1>;
  }
  ```

#### 📁 `assets/`
- Stores **images, fonts, and styles**.
- Example: `src/assets/logo.png`

#### 📁 `hooks/`
- Contains **custom hooks** for state logic.
- Example:
  ```jsx
  // src/hooks/useCounter.js
  import { useState } from 'react';
  export function useCounter() {
    const [count, setCount] = useState(0);
    return { count, setCount };
  }
  ```

#### 📁 `context/`
- Stores **global state** using Context API.
- Example:
  ```jsx
  // src/context/ThemeContext.js
  import { createContext } from 'react';
  export const ThemeContext = createContext(null);
  ```

### 4️⃣ `App.js`
- The **root component** that holds all other components.
- Example:
  ```jsx
  import React from 'react';
  import Home from './pages/Home';
  function App() {
    return <Home />;
  }
  export default App;
  ```

### 5️⃣ `index.js`
- The **entry point** where React renders into `index.html`.
- Example:
  ```jsx
  import React from 'react';
  import ReactDOM from 'react-dom';
  import App from './App';
  ReactDOM.render(<App />, document.getElementById('root'));
  ```

---

## 🎯 Best Practices for Folder Structure
✅ Keep components reusable & modular.  
✅ Organize files into meaningful folders.  
✅ Use Context API or Redux for state management if needed.  
✅ Follow naming conventions (`PascalCase` for components, `camelCase` for hooks).  
✅ Keep styles separate (use `styles.css` or `styled-components`).  

🚀 **Now you're ready to build scalable React apps!** 🚀

