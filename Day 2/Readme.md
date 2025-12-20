# **React Crash Course 2025 – Day 2**

## **Theme of Day 2**

**From Local State to Real Applications**

Day 2 moves learners from **static, local-only components** to **real-world React patterns**:

* Side effects with `useEffect`
* Fetching data from APIs
* Component extraction and composition
* Props as the backbone of React architecture
* Managing growing complexity without frameworks

By the end of Day 2, learners will have a **modular, data-driven React application** that feels like a real production app — not a demo.

---

## **Day 2 Learning Objectives**

By the end of Day 2, learners will be able to:

1. Explain **what side effects are** and why React isolates them
2. Use `useEffect` correctly with dependency arrays
3. Fetch data from an external API and render it safely
4. Handle loading and error states
5. Extract components to reduce complexity
6. Design clean component APIs using props
7. Understand **data ownership** and **state lifting**
8. Avoid common React pitfalls (infinite loops, prop misuse)

---

## **What You’ll Build (Day 2 Outcome)**

You will continue working on the **same React app** started on Day 1.

By the end of Day 2, your app will:

* Load initial data from an API
* Display loading and empty states
* Be broken into reusable components
* Use props for communication
* Have clear separation of concerns

⚠️ **Important:**
This is **not a new app**. Day 2 extends the Day 1 application.

---

## **Key Concepts Covered**

### **1. Side Effects in React**

React components must stay **pure** during rendering.

A **side effect** is anything that:

* Talks to the outside world
* Changes something outside render
* Runs asynchronously

Examples:

* Fetching data
* Reading from localStorage
* Subscribing to events
* Logging

React handles these via `useEffect`.

---

### **2. `useEffect` Mental Model**

Think of `useEffect` as:

> “Run this code **after React updates the screen**.”

```jsx
useEffect(() => {
  // side effect
}, []);
```

Key rules:

* Runs **after render**
* Dependency array controls **when**
* Empty array = run once on mount
* Changing dependency = re-run effect

---

### **3. Fetching Data from an API**

Day 2 introduces **real external data**.

Key patterns:

* Fetch inside `useEffect`
* Use async functions
* Handle loading and errors
* Update state once data arrives

Why this matters:

* Almost all real apps depend on APIs
* Incorrect usage causes infinite re-renders
* This is one of the most common React mistakes

---

### **4. Loading, Error & Empty States**

A professional app never assumes data exists.

You will learn to render:

* Loading indicators
* Error messages
* Empty UI states

This improves:

* UX
* Stability
* Debuggability

---

### **5. Component Extraction**

As components grow, they must be split.

Day 2 focuses on:

* Breaking UI into logical components
* Keeping state in the correct place
* Passing only necessary props

Rule of thumb:

> If a component is doing more than one job — split it.

---

### **6. Props & Data Flow**

Props are:

* Read-only
* Passed from parent → child
* The primary way components communicate

You will learn:

* How props define component contracts
* How callbacks allow children to trigger parent behavior
* Why React enforces one-way data flow

---

### **7. State Ownership & Lifting State**

Key questions introduced:

* Who owns the data?
* Who should modify it?
* Who just displays it?

You will practice:

* Keeping state high enough
* Passing behavior downward
* Avoiding prop drilling (conceptually)

---

## **Project Structure (End of Day 2)**

By the end of Day 2, your project will resemble:

```
src/
 ├─ components/
 │   ├─ TaskList.jsx
 │   ├─ TaskItem.jsx
 ├─ App.jsx
 ├─ main.jsx
 ├─ index.css
```

Each file has a **single responsibility**.

---

## **Common Mistakes Addressed Today**

Day 2 explicitly tackles:

* ❌ Fetching data directly in render
* ❌ Missing dependency arrays
* ❌ Infinite `useEffect` loops
* ❌ Overloading `App.jsx`
* ❌ Passing entire state objects unnecessarily
* ❌ Mutating data from props

---

## **How Day 2 Connects to Day 3**

Day 2 sets the foundation for **scaling the app**.

Day 3 will build on this by adding:

* Persistence
* Advanced state patterns
* Performance awareness
* Final production polish

If Day 1 is *“how React works”*
and Day 2 is *“how real apps are built”*
then Day 3 is *“how React apps survive in production”*.

---

## **End-of-Day Expectations**

By the end of Day 2, learners should:

✅ Be comfortable with `useEffect`
✅ Understand async data flow in React
✅ Be able to split components confidently
✅ Reason about props and state ownership
✅ Read and debug real React code

---

## **Recommended Preparation for Day 3**

Before Day 3:

* Review `useEffect` examples
* Re-read component extraction patterns
* Ensure Day 2 app runs without warnings
* Be comfortable explaining data flow verbally

---
