# **React Crash Course 2025 — Day 2 Quiz**

**Focus Areas:**
`useEffect`, API integration, component extraction, props, side effects, architecture

---

## **Section A — Conceptual Understanding**

### **Q1. What is a “side effect” in React?**

A. Any function that updates state
B. Code that interacts with the outside world (API, timers, storage)
C. Code that runs during rendering
D. JSX that contains JavaScript

**Answer:** **B**

---

### **Q2. Why must side effects NOT run during render?**

A. Rendering is asynchronous
B. Side effects slow down JSX
C. Rendering must remain pure and predictable
D. React forbids async code

**Answer:** **C**

---

### **Q3. When does `useEffect` run?**

A. Before rendering
B. During rendering
C. After the browser updates the DOM
D. Only when props change

**Answer:** **C**

---

### **Q4. What does an empty dependency array (`[]`) mean in `useEffect`?**

A. Effect runs every render
B. Effect runs only when state changes
C. Effect runs once when the component mounts
D. Effect never runs

**Answer:** **C**

---

### **Q5. Why is React’s one-way data flow important?**

A. It improves CSS rendering
B. It allows direct DOM manipulation
C. It makes state changes predictable and debuggable
D. It avoids using props

**Answer:** **C**

---

## **Section B — Code Reading & Prediction**

### **Q6. What happens when this component renders?**

```jsx
useEffect(() => {
  console.log("Hello");
});
```

A. Logs once
B. Logs only when state changes
C. Logs after every render
D. Logs before render

**Answer:** **C**

---

### **Q7. Why does this code cause an infinite loop?**

```jsx
useEffect(() => {
  setCount(count + 1);
}, [count]);
```

**Answer:**

Because updating `count` triggers a re-render, which re-runs the effect, which updates `count` again — causing an infinite render-effect loop.

---

### **Q8. What is wrong with this API fetch?**

```jsx
function App() {
  const [data, setData] = useState([]);

  fetch("/api/data")
    .then(res => res.json())
    .then(setData);

  return <div>{data.length}</div>;
}
```

A. Fetch should be async
B. Fetch must be inside `useEffect`
C. `setData` is invalid
D. JSX cannot display numbers

**Answer:** **B**

---

## **Section C — Multiple Choice (Best Practice)**

### **Q9. Which is the correct way to fetch data on mount?**

A.

```jsx
fetchData();
```

B.

```jsx
useEffect(fetchData, []);
```

C.

```jsx
useEffect(() => {
  fetchData();
}, []);
```

D.

```jsx
useEffect(() => fetchData);
```

**Answer:** **C**

---

### **Q10. Why is this state update incorrect?**

```js
tasks.push(newTask);
setTasks(tasks);
```

A. `push` is slow
B. React does not detect reference changes
C. Arrays cannot be state
D. JSX cannot re-render arrays

**Answer:** **B**

---

## **Section D — Short Answer**

### **Q11. Why do React lists require a `key` prop?**

**Expected Answer:**

To help React identify and efficiently update individual list items during reconciliation, preventing unnecessary DOM re-creation and preserving component state.

---

### **Q12. Who should own application state: parent or child components?**

**Answer:**

Parent components should own shared state. Children receive data via props and notify parents of events via callbacks.

---

### **Q13. What problem does a loading state solve?**

**Answer:**

It prevents blank or confusing UI while data is being fetched and communicates progress to the user.

---

## **Section E — Debugging Scenarios**

### **Q14. Why does this app never stop fetching?**

```jsx
useEffect(() => {
  fetchData();
}, [data]);
```

**Answer:**

Because `fetchData` updates `data`, which retriggers the effect, causing an infinite fetch loop.

---

### **Q15. How would you fix it?**

**Expected Answer:**

Run the effect only once on mount:

```jsx
useEffect(() => {
  fetchData();
}, []);
```

---

## **Section F — Architecture Thinking**

### **Q16. Why extract a `TaskItem` component? (Select ALL that apply)**

A. Cleaner `App.jsx`
B. Easier reuse and testing
C. Improved performance automatically
D. Better separation of concerns

**Correct Answers:** **A, B, D**

---

### **Q17. Why should child components not modify parent state directly?**

**Answer:**

It breaks one-way data flow, makes state changes unpredictable, and complicates debugging.

---

## **Section G — Reflection (Instructor-Led)**

### **Q18. In your own words:**

> “Explain the difference between rendering and side effects in React.”

**Evaluation Criteria:**

✔ Mentions purity of render
✔ Mentions interaction with external systems
✔ Mentions `useEffect`

---

## **Scoring Guide (Optional)**

| Score | Meaning              |
| ----- | -------------------- |
| 16–18 | Strong understanding |
| 13–15 | Ready for Day 3      |
| 10–12 | Needs reinforcement  |
| <10   | Review core concepts |

---
