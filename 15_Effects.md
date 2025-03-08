# ⚡ React Effects – Understanding `useEffect` 🚀

## 📖 **Story Time – The Magic of Side Effects ✨**
Imagine you have a **weather app** that fetches the latest temperature from an API whenever the page loads. But wait! 🌦️ If you fetch the data **inside the render function**, React will keep calling the API **infinitely**! 😨

This is where **`useEffect`** comes to the rescue! It allows us to **run side effects** like data fetching, event listeners, and timers **only when needed**. 🦸‍♂️

---

## 🧐 **What is `useEffect` in React?**
- **`useEffect`** is a React Hook that lets us run **side effects** in function components.
- It runs **after** the component renders.
- It can be controlled to run **once**, **on every render**, or **when dependencies change**.

### 🔥 **Common Side Effects in React**
✅ Fetching data from an API
✅ Updating the DOM manually
✅ Subscribing to events
✅ Managing timers or intervals
✅ Cleaning up resources when a component unmounts

---

## 📂 **Folder Structure for `useEffect` Example**
```
my-app/
│-- src/
│   │-- components/
│   │   │-- FetchWeather.jsx  # 🌦️ Example of API Fetching with useEffect
│   │   │-- Timer.jsx  # ⏳ Example of a Timer with Cleanup
│   │-- App.jsx  # 🔥 Parent Component
│   │-- index.jsx  # 🚀 Entry Point
```

---

## 📝 **Using `useEffect` – Examples & Explanation**
### 1️⃣ **Basic Example – Running `useEffect` on Every Render**
📄 `src/components/FetchWeather.jsx`
```jsx
import React, { useState, useEffect } from 'react';

function FetchWeather() {
  const [temperature, setTemperature] = useState(null);

  useEffect(() => {
    console.log("Fetching weather data...");
    fetch('https://api.example.com/weather')
      .then(response => response.json())
      .then(data => setTemperature(data.temp));
  }); // ⚠️ No dependency array → Runs on every render!

  return (
    <div>
      <h2>Weather App</h2>
      <p>Temperature: {temperature ?? "Loading..."}°C</p>
    </div>
  );
}

export default FetchWeather;
```
⚠️ **Issue:** This will keep fetching data **on every render**, which is inefficient! 😵

---

### 2️⃣ **Running `useEffect` Only Once (on Mount) 🛑**
📄 `src/components/FetchWeather.jsx`
```jsx
useEffect(() => {
  console.log("Fetching weather data...");
  fetch('https://api.example.com/weather')
    .then(response => response.json())
    .then(data => setTemperature(data.temp));
}, []); // ✅ Empty dependency array → Runs only on first render!
```
✅ **Now, it fetches the weather only once when the component mounts!**

---

### 3️⃣ **Running `useEffect` When a Dependency Changes 🔄**
📄 `src/components/FetchWeather.jsx`
```jsx
useEffect(() => {
  console.log("Fetching weather data...");
  fetch(`https://api.example.com/weather?city=${city}`)
    .then(response => response.json())
    .then(data => setTemperature(data.temp));
}, [city]); // ✅ Runs when 'city' changes
```
✅ **Now, it fetches new weather data whenever `city` changes!** 🌍

---

### 4️⃣ **Cleaning Up Effects (Avoid Memory Leaks!) 🚀**
📄 `src/components/Timer.jsx`
```jsx
import React, { useState, useEffect } from 'react';

function Timer() {
  const [seconds, setSeconds] = useState(0);

  useEffect(() => {
    console.log("Starting timer...");
    const interval = setInterval(() => {
      setSeconds(prev => prev + 1);
    }, 1000);

    return () => {
      console.log("Cleaning up timer...");
      clearInterval(interval); // ✅ Cleanup function to stop timer
    };
  }, []);

  return <h2>⏳ Timer: {seconds} seconds</h2>;
}

export default Timer;
```
✅ **The cleanup function ensures the timer is stopped when the component unmounts.**

---

## 🎯 **Best Practices for `useEffect`**
✅ Always **use a dependency array** to control when the effect runs. 📌
✅ **Clean up** effects to prevent memory leaks (especially for timers, event listeners, and subscriptions). 🚀
✅ Avoid unnecessary API calls inside `useEffect` by optimizing dependencies. 🌍
✅ Use **multiple `useEffect` hooks** for different concerns (e.g., one for data fetching, one for event listeners). 🛠️

---

## 🚀 **Final Takeaways**
✅ **`useEffect`** allows us to run **side effects** in function components. 🎯
✅ It can run **on every render**, **once on mount**, or **when dependencies change**. 🔄
✅ Always **clean up** side effects to prevent memory leaks. 🧹

🎉 Now you understand **Effects in React**! Ready for the next topic? 🚀

