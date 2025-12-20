# **React Crash Course 2025 – Day 1 Quiz**

**Duration:** 20–30 minutes
**Format:** MCQ + Short Answer + Code Reasoning
**Passing Benchmark:** 70%
**Goal:** Confirm learners understand **mental models, state, rendering, and tooling**

---

## **Section A: Multiple Choice (Conceptual)**

### **Q1. What problem does React primarily solve?**

A. Faster JavaScript execution
B. Simplifying UI updates by managing DOM changes
C. Server-side rendering
D. Styling web pages

✅ **Correct Answer:** B

---

### **Q2. React is best described as:**

A. A full-stack framework
B. A backend JavaScript runtime
C. A front-end UI library
D. A CSS preprocessor

✅ **Correct Answer:** C

---

### **Q3. In React, the UI is best described as:**

A. A static HTML template
B. A function of state
C. A set of DOM commands
D. A compiled asset

✅ **Correct Answer:** B

---

### **Q4. What happens when React state is updated?**

A. The browser reloads
B. The DOM is rebuilt entirely
C. The component function re-runs
D. JavaScript stops execution

✅ **Correct Answer:** C

---

### **Q5. What is the purpose of the Virtual DOM?**

A. Replace the browser DOM
B. Store application state
C. Optimize DOM updates via diffing
D. Style UI components

✅ **Correct Answer:** C

---

### **Q6. Which statement about React data flow is correct?**

A. Data flows in both directions
B. Child components control parent state
C. Data flows downward via props
D. State is global by default

✅ **Correct Answer:** C

---

### **Q7. Why does React require keys when rendering lists?**

A. To satisfy JSX syntax
B. To improve JavaScript performance
C. To identify elements across renders
D. To sort list items

✅ **Correct Answer:** C

---

### **Q8. Which tool is used to scaffold a modern React app in this course?**

A. Webpack
B. Create React App
C. Vite
D. Babel

✅ **Correct Answer:** C

---

## **Section B: Multiple Choice (Code Understanding)**

### **Q9. What is wrong with the following code?**

```js
const addItem = () => {
  items.push("New Item");
  setItems(items);
};
```

A. Nothing, this is valid
B. `push` mutates state directly
C. `setItems` should not be called
D. Arrays cannot be used in state

✅ **Correct Answer:** B

---

### **Q10. Which version correctly updates state?**

A.

```js
setItems(items.push("New"));
```

B.

```js
setItems(items = ["New"]);
```

C.

```js
setItems([...items, "New"]);
```

D.

```js
items = [...items];
```

✅ **Correct Answer:** C

---

## **Section C: Short Answer (Explain in Your Own Words)**

### **Q11. Explain the difference between declarative and imperative UI.**

**Expected Answer (Key Points):**

* Imperative: tell the browser how to change the DOM
* Declarative: describe what the UI should look like based on state
* React handles the DOM updates automatically

---

### **Q12. What does `useState` do?**

**Expected Answer:**

* Stores component state
* Provides a setter function
* Triggers a re-render when state changes

---

### **Q13. Why must React state be treated as immutable?**

**Expected Answer:**

* React detects changes by reference
* Mutating state does not create a new reference
* Immutable updates allow React to re-render correctly

---

### **Q14. Why should array index NOT be used as a key in dynamic lists?**

**Expected Answer:**

* Causes incorrect DOM reuse
* Breaks UI when items are reordered or deleted
* Leads to subtle bugs

---

## **Section D: Code Reasoning (No Coding Required)**

### **Q15. What will happen when the button is clicked?**

```jsx
const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>
  Click
</button>
```

A. The page reloads
B. The DOM updates manually
C. The component re-renders with count increased
D. Nothing happens

✅ **Correct Answer:** C

---

### **Q16. What is wrong with this JSX?**

```jsx
return (
  <h1>Hello</h1>
  <p>World</p>
);
```

**Expected Answer:**

* JSX must return a single root element
* Needs a wrapper or fragment

---

## **Section E: Tooling & Environment**

### **Q17. Why is Node.js required for React development?**

**Expected Answer:**

* Provides npm
* Runs build tools and dev server
* Required for Vite

---

### **Q18. What is one advantage of Vite over traditional bundlers?**

**Expected Answer:**

* Faster startup
* Native ES modules
* Faster HMR

---

## **Section F: Reflection (Optional but Recommended)**

### **Q19. What concept from Day 1 was hardest to understand and why?**

(Open-ended)

---

### **Q20. What is one thing React does that surprised you?**

(Open-ended)

---

## **Scoring Guide**

| Section        | Points |
| -------------- | ------ |
| MCQ            | 10     |
| Short Answer   | 6      |
| Code Reasoning | 4      |
| **Total**      | **20** |

* **16–20:** Strong foundation
* **13–15:** Ready for Day 2
* **<13:** Review `useState`, rendering, immutability

---
