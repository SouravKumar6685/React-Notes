# 🔥 React Purity – Writing Clean & Predictable Code 🚀

## 📖 **Story Time – The Power of Pure Functions ✨**
Imagine you are making a calculator app. Every time a user clicks a button, the app should calculate a new value and display it. But sometimes, the app gives **unexpected results** because the function is modifying external values. 😨

That’s where **Purity** in React comes in! Writing **pure functions** ensures that your components behave **predictably** and don’t cause side effects. 🔥

---

## 🧐 **What is Purity in React?**
A function is **pure** if:
1. It **always** returns the same output for the same input. 🎯
2. It **does not modify** external variables or state. ✅
3. It **has no side effects** (e.g., no API calls, no modifying DOM). 🚀

---

## 📂 **Folder Structure for Purity Example**
```
my-app/
│-- src/
│   │-- components/
│   │   │-- PureCalculator.jsx  # 📝 Example of a Pure Function
│   │   │-- ImpureCounter.jsx  # ⚠️ Example of an Impure Function
│   │-- App.jsx  # 🔥 Parent Component
│   │-- index.jsx  # 🚀 Entry Point
```

---

## 📝 **Pure Functions vs Impure Functions in React**
### 1️⃣ **Pure Function – Always Returns the Same Output** ✅
📄 `src/components/PureCalculator.jsx`
```jsx
import React from 'react';

// ✅ Pure Function - No Side Effects, Always Returns the Same Output
function add(a, b) {
  return a + b;
}

function PureCalculator() {
  return (
    <div>
      <h2>Pure Function Example</h2>
      <p>10 + 5 = {add(10, 5)}</p>
    </div>
  );
}

export default PureCalculator;
```
✅ **Why is this function pure?**
- It **always** returns the same sum for the same `a` and `b`.
- It **does not modify** any external variables.
- It has **no side effects** (e.g., no API calls, no DOM updates).

---

### 2️⃣ **Impure Function – Changes External State** ❌
📄 `src/components/ImpureCounter.jsx`
```jsx
import React, { useState } from 'react';

let count = 0; // ❌ External variable

function impureIncrement() {
  count += 1; // ❌ Modifying external state
  return count;
}

function ImpureCounter() {
  const [value, setValue] = useState(0);

  return (
    <div>
      <h2>Impure Function Example</h2>
      <p>Count: {value}</p>
      <button onClick={() => setValue(impureIncrement())}>Increment</button>
    </div>
  );
}

export default ImpureCounter;
```
❌ **Why is this function impure?**
- It **modifies** an external variable (`count`).
- The result depends on **past calls** (not just inputs).
- It may cause **unexpected behavior** if used in different places.

---

## 🎯 **Best Practices for Purity in React**
✅ Use **pure functions** for calculations and rendering components. 🎯
✅ **Avoid modifying external variables** inside components. 🚫
✅ **Use state properly** (`useState`, `useReducer`) to update values. 🔄
✅ Keep components **stateless and predictable** whenever possible. 🧑‍💻

---

## 🚀 **Final Takeaways**
✅ **Pure functions** make React apps **more predictable & testable**. 🔥
✅ **Impure functions** can cause **unexpected behavior** & bugs. 😵
✅ Follow **React’s declarative approach** by using **pure components**.

🎉 Now you understand the importance of **Purity in React**! Ready for the next topic? 🚀

