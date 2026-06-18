# **Curriculum**

This program is designed for **engineers** who want a deep understanding of React: from mental models and architecture to building production-ready apps with modern tooling.

---

## **Day 1: Core React Mental Models & Tooling**

### **Module 1: React Mental Model**

#### **1.1 Declarative vs Imperative UI**

* Imperative JS: direct DOM manipulation
* React: declarative, describe the UI for a given state
* 💡 Think: **state → UI**, not **UI → state**

**Exercise:** Convert a vanilla JS counter app to React declarative state-based counter.

---

#### **1.2 Virtual DOM & Reconciliation**

* Virtual DOM = lightweight memory representation
* Reconciliation = minimal updates to the real DOM
* Performance benefits, avoids unnecessary re-renders

**Discussion:** Why React scales better for large apps vs jQuery/Vanilla JS.

---

#### **1.3 One-Way Data Flow & Props**

* Data flows downward; state lives in parent components
* Children communicate via callback props
* Predictable updates → easier debugging

**Exercise:** Build a counter with parent holding state and child receiving props & triggering increment via callback.

---

### **Module 2: Modern Tooling**

#### **2.1 Why Vite?**

* Native ES Modules → instant server start
* Lightning-fast HMR
* `esbuild` pre-bundling

**Comparison:** Demo cold-start speed of Vite vs Webpack for same app.

---

#### **2.2 Node.js & NPM**

* Node provides runtime + package management
* Verify LTS versions:

```bash
node -v
npm -v
```

**Tip:** Always use LTS for stability.

---

#### **2.3 Project Scaffolding & Directory Structure**

```bash
npm create vite@latest taskmaster-app -- --template react
cd taskmaster-app
npm install
npm run dev
```

```
src/
 ├─ main.jsx      # entry point
 ├─ App.jsx       # root component
 ├─ components/   # reusable UI pieces
 ├─ App.css       # styles
```

**Exercise:** Scaffold app, navigate folder, inspect project structure.

---

## **Day 2: Components, State, and Hooks**

### **Module 3: JSX & Functional Components**

* JSX = JS + XML-like syntax
* Rules: single root, `{}` for JS expressions, `className`, `htmlFor`

**Exercise:** Build a simple greeting component using props.

---

### **Module 4: State Management with Hooks**

#### **4.1 useState**

* Holds dynamic data → triggers re-render on update
* **Immutability rule:**

```js
setTasks([...tasks, newTask]);
```

*Exercise:* Build a to-do input + list using `useState`.

---

#### **4.2 useEffect**

* Replace lifecycle methods
* Fetch API, subscribe to events, log, animate
* Dependency array controls re-runs

```jsx
useEffect(() => {
  console.log("Component mounted");
}, []);
```

**Exercise:** Log input value changes with `useEffect`.

---

### **Module 5: Building TaskMaster Pro**

**Features Covered:**

* State management
* Conditional rendering
* List rendering
* Event handling

**Step-by-step App Code:** *(See prior App.jsx example)*

**Exercise:** Add task, delete task, render list with keys.

---

### **Module 6: Advanced Patterns**

* Immutability → trigger Virtual DOM diffing
* Keys → unique IDs in lists
* Conditional rendering → ternary / short-circuit
* Event handlers → pass via props

**Exercise:** Add “mark complete” functionality and conditional styling.

---

## **Day 3: APIs, Component Patterns & Performance**

### **Module 7: API Integration**

* `useEffect` + fetch
* Loading state + error handling
* Conditional rendering for UX

**Exercise:** Fetch initial tasks from JSONPlaceholder API and display.

---

### **Module 8: Component Extraction & Props**

* Extract `TaskItem` and `TaskList`
* Pass data and callbacks via props
* Benefits: modularity, reusability, readability

```jsx
<TaskList tasks={tasks} onDelete={deleteTask} />
```

**Exercise:** Refactor TaskMaster Pro into separate components.

---

### **Module 9: Persisting Data**

* LocalStorage to survive reloads
* Sync state with side effects using `useEffect`

```jsx
useEffect(() => {
  localStorage.setItem("tasks", JSON.stringify(tasks));
}, [tasks]);
```

**Exercise:** Ensure tasks remain after refresh.

---

### **Module 10: Filters, Conditional UI, & UX Enhancements**

* Filter tasks by status: all, active, completed
* Conditional rendering for empty state, completed tasks
* Optional: CSS animations for task addition/removal

```jsx
const filtered = tasks.filter(task => filter === "active" ? !task.completed : true);
```

**Exercise:** Implement filter buttons + styling for completed tasks.

---

### **Module 11: Performance & Best Practices**

* `useMemo` / `useCallback` to avoid unnecessary recalculations
* Keep components small and focused
* Debugging with React DevTools
* Prop destructuring, minimal prop drilling
* Key takeaways:

  1. Declarative UI
  2. Virtual DOM efficiency
  3. One-way data flow
  4. Immutability
  5. Hooks for state & effects
  6. Component modularity
  7. Modern tooling (Vite + ES Modules)

---

### **Capstone Exercise: Build a Production-ready App**

**TaskMaster Pro – API Edition:**

* Fetch tasks from API
* Add / delete / mark complete
* Persist tasks in LocalStorage
* Filter tasks
* Modular components (`TaskList`, `TaskItem`)

**Discussion:** Refactor for scalability and performance, consider context, and plan for further enhancements (authentication, backend integration).

---

This structure **spreads naturally across 3 days**, mixing **theory, code walkthroughs, hands-on exercises, and discussion**, while covering:

* Core mental models
* Tooling and scaffolding
* JSX, components, hooks
* State management and immutability
* Conditional rendering and events
* API integration
* Component extraction and props
* Persistence, filters, and UX
* Performance, debugging, and best practices

---
