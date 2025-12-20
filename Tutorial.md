# **React Crash Course 2025 **

This guide is designed for **engineers who want to understand React**, from mental models, architecture, tooling, to implementing a fully-featured app.

It covers:

* React architecture & mental models
* Modern tooling (Vite, Node.js, npm)
* Functional components, hooks, and state management
* Advanced patterns: immutability, reconciliation, conditional rendering
* Best practices, debugging, and performance
* Step-by-step production-ready app

---

## **Module 1: React Mental Model – How React Thinks**

### **1.1 Declarative vs Imperative UI**

**Imperative JavaScript**: You instruct the DOM exactly how to update.

```js
document.getElementById("title").innerText = "Hello";
```

* Pros: Direct control
* Cons: Manual state management, error-prone

**React (Declarative)**: You declare what the UI should look like for a given state.

```jsx
<h1>{title}</h1>
```

* React handles synchronization with the browser
* Less bugs, scalable for large apps

💡 **Tip:** Think in terms of *state → UI*, not *UI → state*.

---

### **1.2 Virtual DOM & Reconciliation**

* React keeps a **lightweight Virtual DOM** in memory.
* When state changes:

  1. A new Virtual DOM tree is created.
  2. Diffing identifies minimal changes.
  3. Only affected real DOM nodes are updated.

**Why it matters**: Direct DOM manipulations are expensive. Reconciliation keeps apps **fast and efficient**.

---

### **1.3 One-Way Data Flow**

* Data moves **downwards** from parent to child via **props**.
* Children communicate changes via **callbacks**.

```jsx
<Child onChange={handleChange} />
```

* Predictable updates
* Easier to debug
* State ownership is clear

---

## **Module 2: React Tooling in 2025**

### **2.1 Why Vite?**

* Traditional bundlers (Webpack) crawl and bundle the entire app → slow cold starts
* Vite uses **Native ES Modules**:

  * Instant start
  * On-demand module loading
  * Lightning-fast Hot Module Replacement (HMR)
  * Uses **esbuild** (Go-based) for pre-bundling

**Result:** Near-instant dev server even for large apps.

---

### **2.2 Node.js & NPM**

* Node.js provides runtime and npm package management
* Installation verification:

```bash
node -v
npm -v
```

* Always use **LTS version** for stability

---

### **2.3 Project Scaffold**

```bash
npm create vite@latest taskmaster-app -- --template react
cd taskmaster-app
npm install
npm run dev
```

Directory layout:

```
src/
 ├─ main.jsx      # React entry point
 ├─ App.jsx       # Root component
 ├─ components/   # Reusable UI pieces
 ├─ App.css       # Styles
```

💡 **Tip:** Keep components modular and reusable for maintainability.

---

## **Module 3: JSX, Components, and Hooks**

### **3.1 JSX Rules**

* One root element per component
* JavaScript expressions inside `{ }`
* Use `className` instead of `class`, `htmlFor` instead of `for`

```jsx
<h1 className="title">{title}</h1>
```

---

### **3.2 Functional Components**

* Modern React prefers **functions over classes**
* Return JSX
* Receive **props**
* Can manage internal **state with hooks**

```jsx
function App({ greeting }) {
  return <h1>{greeting}</h1>;
}
```

---

### **3.3 useState: Internal Component State**

* Holds dynamic data
* Updating state triggers re-render

```jsx
const [tasks, setTasks] = useState([]);
```

* **Immutability rule:** Always create a new array/object when updating state

  ```js
  setTasks([...tasks, newTask]);
  ```

---

### **3.4 useEffect: Side Effects**

* Replace lifecycle methods (componentDidMount, componentDidUpdate)
* Common use cases:

  * Fetching API data
  * Subscribing to events
  * Logging, animations

```jsx
useEffect(() => {
  console.log("Component mounted");
}, []);
```

* Empty array → run once
* Dependency array → run when dependency changes

---

## **Module 4: Building “TaskMaster Pro”**

A fully-featured task manager to demonstrate:

* State management
* Immutability
* Conditional rendering
* Lists and keys

---

### **4.1 App Component (Step by Step)**

```jsx
import { useState } from "react";
import "./App.css";

function App() {
  const [tasks, setTasks] = useState([]);
  const [input, setInput] = useState("");

  // Add a task
  const addTask = (e) => {
    e.preventDefault();
    if (!input.trim()) return;

    const newTask = { id: crypto.randomUUID(), text: input, completed: false };
    setTasks([...tasks, newTask]); // Immutability triggers re-render
    setInput("");
  };

  // Delete a task
  const deleteTask = (id) => setTasks(tasks.filter(task => task.id !== id));

  return (
    <div className="app-container">
      <h1>TaskMaster Pro</h1>

      <form onSubmit={addTask}>
        <input value={input} onChange={(e) => setInput(e.target.value)} />
        <button>Add Task</button>
      </form>

      {tasks.length === 0 ? (
        <p>No tasks yet</p>
      ) : (
        <ul>
          {tasks.map(task => (
            <li key={task.id}>
              {task.text}
              <button onClick={() => deleteTask(task.id)}>❌</button>
            </li>
          ))}
        </ul>
      )}
    </div>
  );
}

export default App;
```

---

### **4.2 Step-by-Step Explanation**

1. **Form submission**:

   * `preventDefault` stops page reload
   * Validate input
2. **Add task**:

   * New object
   * Immutable array spread
3. **Delete task**:

   * Filter out by ID
   * React updates the DOM efficiently
4. **Render list**:

   * Use `key` for reconciliation
   * Conditional render empty state

---

## **Module 5: Advanced Patterns & Best Practices**

### **5.1 Immutability**

Always create **new objects/arrays** for state changes.

* ✅ `setTasks([...tasks, newTask])`
* ❌ `tasks.push(newTask)`

Why:

* React detects changes via reference
* Triggers Virtual DOM diffing

---

### **5.2 Keys in Lists**

* Unique ID per item
* Prevents DOM re-creation
* Maintains state in dynamic lists

```jsx
{tasks.map(task => <li key={task.id}>{task.text}</li>)}
```

---

### **5.3 Conditional Rendering**

```jsx
{tasks.length === 0 ? <p>No tasks</p> : <ul>...</ul>}
{completed && <span>✔</span>}
```

---

### **5.4 Event Handling & Props**

* Pass functions via props to children
* Child triggers function to update parent state

```jsx
<ChildComponent onDelete={handleDelete} />
```

---

### **5.5 Performance Awareness**

* Use `useMemo` and `useCallback` for expensive calculations or functions
* Avoid unnecessary re-renders
* Keep components small and focused

---

### **5.6 Debugging Tips**

* Check state with `console.log()`
* React DevTools to inspect component tree
* Keys missing → warnings
* Uncontrolled vs controlled components → input issues

---

## **Module 6: Extending TaskMaster Pro**

* Add **task completion toggle**
* Add **local storage persistence**
* Extract **TaskItem component**
* Add **filters** (all, active, completed)

---

### **6.1 Example: Extract TaskItem Component**

```jsx
function TaskItem({ task, onDelete }) {
  return (
    <li>
      <span>{task.text}</span>
      <button onClick={() => onDelete(task.id)}>❌</button>
    </li>
  );
}
```

* Benefits:

  * Cleaner App.jsx
  * Reusable component
  * Easier to test

---

### **6.2 Persisting Tasks in Local Storage**

```jsx
useEffect(() => {
  const saved = JSON.parse(localStorage.getItem("tasks")) || [];
  setTasks(saved);
}, []);

useEffect(() => {
  localStorage.setItem("tasks", JSON.stringify(tasks));
}, [tasks]);
```

* Tasks survive page reload
* Learn about side effects + dependency arrays

---

### **6.3 Conditional Rendering with Filters**

```jsx
const filtered = tasks.filter(task => filter === "active" ? !task.completed : true);
```

---

## **Module 7: Key Takeaways**

1. **React is declarative** – describe UI state, not DOM instructions
2. **Virtual DOM** – efficient rendering
3. **One-way data flow** – predictable, easy to debug
4. **Immutability** – key to state updates
5. **Hooks** – manage state and side effects
6. **Modular Components** – reusable and maintainable
7. **Vite + ES Modules** – modern, lightning-fast tooling

---

## **Module 8: API Integration with `useEffect`**

### **8.1 Fetching Data from an API**

React apps often need external data. Use `useEffect` for side effects like fetching.

```jsx
import { useState, useEffect } from "react";

function App() {
  const [todos, setTodos] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    async function fetchTodos() {
      try {
        const res = await fetch("https://jsonplaceholder.typicode.com/todos?_limit=5");
        const data = await res.json();
        setTodos(data);
      } catch (error) {
        console.error("Error fetching todos:", error);
      } finally {
        setLoading(false);
      }
    }
    fetchTodos();
  }, []); // Empty dependency array → run once on mount

  if (loading) return <p>Loading tasks...</p>;

  return (
    <div>
      <h1>Todo List</h1>
      <ul>
        {todos.map(todo => (
          <li key={todo.id}>
            {todo.title} {todo.completed ? "✔" : "❌"}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;
```

**Step-by-step Explanation:**

1. **State initialization:** `todos` for data, `loading` for spinner.
2. **`useEffect`:** Runs once when component mounts.
3. **Async API call:** Use `fetch` or `axios`.
4. **Update state:** `setTodos(data)` triggers a re-render.
5. **Conditional rendering:** Show "Loading..." while fetching.

---

### **8.2 Why `useEffect`?**

* Side effects should not block rendering
* Fetching inside `useEffect` ensures React lifecycle compliance
* Dependency array controls when effect runs
* Avoid infinite loops by careful dependency management

---

## **Module 9: Component Extraction & Props**

### **9.1 Extracting a TaskItem Component**

Large components become hard to manage. Extract reusable units.

```jsx
function TaskItem({ task, onDelete }) {
  return (
    <li>
      <span>{task.text}</span>
      <button onClick={() => onDelete(task.id)}>Delete</button>
    </li>
  );
}
```

**Benefits:**

* Modular & reusable
* Cleaner `App.jsx`
* Easier testing

---

### **9.2 Using Props Effectively**

* Props are **read-only**
* Children cannot modify parent state directly
* Pass **callback functions** to update parent

```jsx
function TaskList({ tasks, onDelete }) {
  return (
    <ul>
      {tasks.map(task => (
        <TaskItem key={task.id} task={task} onDelete={onDelete} />
      ))}
    </ul>
  );
}
```

* `TaskList` receives data and delete function
* Delegates task rendering to `TaskItem`
* Keeps responsibilities separated

---

### **9.3 Updated App Component with Component Extraction**

```jsx
import { useState, useEffect } from "react";
import TaskList from "./components/TaskList";

function App() {
  const [tasks, setTasks] = useState([]);
  const [input, setInput] = useState("");

  // Add Task
  const addTask = (e) => {
    e.preventDefault();
    if (!input.trim()) return;

    const newTask = { id: crypto.randomUUID(), text: input, completed: false };
    setTasks([...tasks, newTask]);
    setInput("");
  };

  // Delete Task
  const deleteTask = (id) => setTasks(tasks.filter(task => task.id !== id));

  // Fetch initial tasks from API
  useEffect(() => {
    async function fetchTasks() {
      try {
        const res = await fetch("https://jsonplaceholder.typicode.com/todos?_limit=5");
        const data = await res.json();
        setTasks(data.map(item => ({ id: item.id, text: item.title, completed: item.completed })));
      } catch (error) {
        console.error("API fetch failed:", error);
      }
    }
    fetchTasks();
  }, []);

  return (
    <div className="app-container">
      <h1>TaskMaster Pro – API Edition</h1>
      <form onSubmit={addTask}>
        <input value={input} onChange={(e) => setInput(e.target.value)} placeholder="Add new task..." />
        <button>Add</button>
      </form>
      {tasks.length === 0 ? <p>No tasks!</p> : <TaskList tasks={tasks} onDelete={deleteTask} />}
    </div>
  );
}

export default App;
```

**Notes:**

* `TaskList` handles rendering
* `TaskItem` handles individual task UI
* `App` manages state and API

---

### **9.4 Best Practices with Props**

1. Keep props **minimal** – only pass necessary data
2. Use **destructuring** to improve readability
3. Avoid unnecessary prop drilling – consider context for deeply nested components
4. Validate props with `PropTypes` (optional but recommended)

---

### **9.5 Conditional Rendering & API Integration**

* Show loading states for API calls
* Show empty states for no tasks
* Show completed tasks differently

```jsx
{tasks.length === 0 ? <p>No tasks</p> : <TaskList tasks={tasks} onDelete={deleteTask} />}
```

* Combine with CSS classes to indicate completion status
* Supports user-friendly UX

---

### **9.6 Summary – API + Components**

* `useEffect` integrates React with APIs and side effects
* Component extraction improves readability and maintainability
* Props provide controlled data flow
* Combined patterns produce **production-ready applications**

---

At this stage, your **TaskMaster Pro** app:

* Fetches initial tasks from an API
* Allows adding and deleting tasks
* Uses **extracted components** (`TaskList` + `TaskItem`)
* Demonstrates **state management, props, and API side effects**


