# Day 1: Foundations & Tooling

Welcome to **Day 1** of the React Crash Course! Today, we focus on **React architecture, mental models, and modern tooling**. By the end of this session, you will understand how React thinks, why it is fast, and how to scaffold a new React project with Vite.

---

## **Learning Objectives**

By the end of Day 1, learners will be able to:

1. Understand **Declarative vs Imperative UI**
2. Explain the **Virtual DOM & Reconciliation**
3. Describe **one-way data flow and props**
4. Set up a **React project using Vite**
5. Understand directory structure and best practices

---

## **Module 1: React Mental Model**

### **1.1 Declarative vs Imperative UI**

* **Imperative JS** – manually instruct the DOM:

```js
document.getElementById("title").innerText = "Hello";
```

* **Declarative React** – declare UI based on state:

```jsx
<h1>{title}</h1>
```

**Key Points:**

* React automatically synchronizes the UI with state
* Predictable and scalable for large applications
* Think in terms of **state → UI**, not **UI → state**

---

### **1.2 Virtual DOM & Reconciliation**

* React maintains a lightweight **Virtual DOM** in memory.
* **Process:**

  1. State changes → new Virtual DOM tree
  2. Diffing → find minimal changes
  3. Reconciliation → update only necessary real DOM nodes

**Why it matters:** Minimizes expensive DOM operations for high performance.

---

### **1.3 One-Way Data Flow**

* **Parent → Child** via **props**
* **Child → Parent** via **callbacks**
* Predictable updates, easier debugging, clear state ownership

```jsx
<Child onChange={handleChange} />
```

---

## **Module 2: Tooling in 2025**

### **2.1 Node.js & npm**

* Node.js provides JavaScript runtime outside the browser
* npm handles package management
* Verify installation:

```bash
node -v
npm -v
```

* Use **LTS version** for stability

---

### **2.2 Why Vite?**

* Traditional bundlers (Webpack) are slow for large apps
* **Vite advantages:**

  * Instant start
  * On-demand module loading
  * Lightning-fast HMR
  * Uses **esbuild** for pre-bundling

---

### **2.3 Scaffolding a React Project**

```bash
# Create project with React template
npm create vite@latest taskmaster-app -- --template react

# Navigate into project
cd taskmaster-app

# Install dependencies
npm install

# Start development server
npm run dev
```

**Directory Layout:**

```
src/
 ├─ main.jsx      # entry point
 ├─ App.jsx       # root component
 ├─ components/   # reusable UI pieces
 ├─ App.css       # styles
```

💡 **Tip:** Keep components modular and reusable.

---

## **Day 1 Summary**

* React is **declarative** – you describe the UI for a given state
* **Virtual DOM** ensures efficient rendering
* Data flows **one-way** – predictable updates
* Vite + Node.js provide **fast, modern tooling**
* Scaffolded projects should follow **modular directory structures**

---

