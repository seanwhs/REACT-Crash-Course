# **Slide 1 – React Crash Course 2025: Day 1**

**Title:** Foundations & Tooling

**Content:**

* **Learning Objectives:**

  * Declarative vs Imperative UI
  * Virtual DOM & Reconciliation
  * One-way data flow & props
  * Modern tooling: Vite + Node.js
  * Project scaffold & components

*(Visual: roadmap icon or arrow from “Concepts → Tooling → Components”)*

---

# **Slide 2 – Declarative vs Imperative UI**

**Left Side:**
**Imperative JS**

```js
document.getElementById("title").innerText = "Hello";
```

* Manual DOM updates
* Error-prone, hard to scale

**Right Side:**
**React Declarative**

```jsx
<h1>{title}</h1>
```

* Describe **what** the UI should look like
* React handles updates automatically

*(Visual: arrows showing “state → UI” for React vs “UI → DOM” for JS)*

---

# **Slide 3 – Virtual DOM & Reconciliation**

**Content:**

* React keeps a **lightweight in-memory DOM**
* **Diffing:** detects minimal changes
* **Reconciliation:** updates only necessary DOM nodes

**Diagram:**

```
State Change → New Virtual DOM → Diff → Update Real DOM
```

💡 **Tip:** Avoid direct DOM manipulation; rely on state + Virtual DOM

---

# **Slide 4 – One-Way Data Flow**

**Content:**

* Parent → Child = **props**
* Child → Parent = **callback functions**

**Diagram:**

```
Parent Component
  └─ passes data (props) ─> Child Component
Child Component
  └─ triggers callback ─> Parent Component updates state
```

* Predictable & easier to debug

---

# **Slide 5 – Tooling in 2025**

**Vite + Node.js**

* **Node.js:** runtime + npm
* **Vite Advantages:**

  * Native ES Modules → instant start
  * Lightning-fast HMR
  * esbuild pre-bundling
  * On-demand module loading

*(Visual: small icon stack: Node.js → Vite → Browser)*

---

# **Slide 6 – Scaffold a React Project**

**Commands:**

```bash
npm create vite@latest taskmaster-app -- --template react
cd taskmaster-app
npm install
npm run dev
```

**Directory Layout Diagram:**

```
taskmaster-app/
 ├─ src/
 │   ├─ main.jsx      # Entry point
 │   ├─ App.jsx       # Root component
 │   ├─ components/   # Reusable UI pieces
 │   └─ App.css       # Styles
```

💡 **Tip:** Modular & reusable components = maintainable code

---

# **Slide 7 – JSX & Component Basics**

**JSX Rules:**

* One root element per component
* `{ }` for JS expressions
* `className` instead of `class`

**Example:**

```jsx
function App({ greeting }) {
  return <h1>{greeting}</h1>;
}
```

*(Visual: JSX bridging JS → HTML)*

---

# **Slide 8 – Day 1 Key Takeaways**

* React is **declarative** → focus on state → UI
* Virtual DOM → efficient updates
* One-way data flow → predictable & debug-friendly
* Vite + Node.js → modern, lightning-fast tooling
* Scaffolded projects should be modular & reusable
* JSX bridges JS and HTML
* Immutability + props = foundational for state management

*(Visual: checklist or icons representing each takeaway)*

---


