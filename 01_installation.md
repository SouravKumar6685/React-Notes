# React Installation Guide



## Prerequisites
Before installing React, make sure you have the following installed:
- **Node.js** (Latest LTS version recommended) – [Download Here](https://nodejs.org/)
- **npm** or **yarn** (Comes with Node.js)
- **A code editor** (VS Code recommended) – [Download VS Code](https://code.visualstudio.com/)

---

![](https://imgs.search.brave.com/AcZGc1BPrBP0gbG8hZDgknJTJHRD21pFUw6eHZWFFFw/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly93d3cu/aW50ZXJzeW5lcmd5/LnBsL3dwLWNvbnRl/bnQvdXBsb2Fkcy8y/MDI0LzA3L1JlYWN0/anMtU29mdHdhcmUt/SG91c2Uuc3Zn)

## Install React using Create React App
This is the easiest way to set up a React project with all necessary configurations.

### 1️⃣ Create a New React App
```sh
npx create-react-app my-app
```
👉 If `npx` is not installed, install it using:
```sh
npm install -g npx
```

**Alternative (Using npm or yarn):**
```sh
npm init react-app my-app
```
or
```sh
yarn create react-app my-app
```

### 2️⃣ Navigate to Project Directory
```sh
cd my-app
```

### 3️⃣ Start the Development Server
```sh
npm start
```
or
```sh
yarn start
```
🔹 This will start a local development server at `http://localhost:3000/`.

---

## Install React Manually (Without Create React App)
If you want to manually set up React with Webpack and Babel:

### 1️⃣ Create a Project Folder
```sh
mkdir my-app && cd my-app
```

### 2️⃣ Initialize a Package.json
```sh
npm init -y
```

### 3️⃣ Install React and React DOM
```sh
npm install react react-dom
```

### 4️⃣ Install Development Dependencies
```sh
npm install webpack webpack-cli webpack-dev-server babel-loader @babel/core @babel/preset-env @babel/preset-react html-webpack-plugin css-loader style-loader --save-dev
```

### 5️⃣ Create Necessary Files
- **`index.html`**
- **`index.js`**
- **`webpack.config.js`**
- **`.babelrc`**

_(For configuration details, let me know!)_

### 6️⃣ Run the Project
```sh
npx webpack serve --mode development
```

---

## Verify Installation
To check if React is installed correctly, create a simple component in `src/App.js`:
```jsx
import React from 'react';

function App() {
  return <h1>Hello, React! 🚀</h1>;
}

export default App;
```

Run the app using:
```sh
npm start
```
If you see `Hello, React! 🚀` in your browser, React is successfully installed! 🎉

---

## Next Steps
Now that React is installed, start learning its core concepts:
✅ Components  
✅ JSX  
✅ Props & State  
✅ Hooks  

🚀 Happy Coding! 🚀

