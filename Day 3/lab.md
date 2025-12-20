# **React Crash Course 2025 – Day 3 Lab Instructions**

Welcome to **Day 3** of your React Crash Course. Today, you will extend your React application to a **production-ready Todo/Task Management App** with **API integration, component extraction, hooks, and state management**.

By the end of the lab, your app will include:

* **Persistent state** via `localStorage`
* **API data fetching** using `useEffect`
* **Modular components** (`TaskList`, `TaskItem`)
* **Controlled components for forms**
* **Conditional rendering** and filtering (All, Active, Completed)
* **Production-ready best practices**

---

## **Pre-requisites**

* Completion of **Day 1 & Day 2 labs**
* Node.js & npm installed (LTS version)
* Vite scaffolded React project (`npm create vite@latest`)
* Basic familiarity with `useState`, `useEffect`, props, and JSX

---

## **Lab Objectives**

1. **Extract Components**

   * Move task rendering into reusable `TaskItem` and `TaskList` components.
2. **Implement API Integration**

   * Fetch tasks from a public API (`JSONPlaceholder`) and map them to your state.
3. **Persist State in Local Storage**

   * Tasks should survive page reloads.
4. **Add Filters**

   * Filter tasks: All, Active, Completed.
5. **Enhance UX**

   * Conditional rendering for empty states and loading states.

---

## **Step 1 – Component Extraction**

* Create `components/TaskItem.jsx` and `components/TaskList.jsx`
* TaskItem receives props: `task` and `onDelete`
* TaskList receives: `tasks` array and `onDelete` callback

```jsx
// TaskItem.jsx
export default function TaskItem({ task, onDelete }) {
  return (
    <li>
      <span>{task.text}</span>
      <button onClick={() => onDelete(task.id)}>Delete</button>
    </li>
  );
}
```

```jsx
// TaskList.jsx
import TaskItem from "./TaskItem";

export default function TaskList({ tasks, onDelete }) {
  return (
    <ul>
      {tasks.map(task => (
        <TaskItem key={task.id} task={task} onDelete={onDelete} />
      ))}
    </ul>
  );
}
```

---

## **Step 2 – API Integration**

* Use `useEffect` to fetch initial tasks from API.
* Map the API response to match your app's task shape.

```jsx
useEffect(() => {
  async function fetchTasks() {
    const res = await fetch("https://jsonplaceholder.typicode.com/todos?_limit=5");
    const data = await res.json();
    setTasks(data.map(item => ({
      id: item.id,
      text: item.title,
      completed: item.completed
    })));
  }
  fetchTasks();
}, []);
```

---

## **Step 3 – Local Storage Persistence**

* Save tasks whenever they update

```jsx
useEffect(() => {
  localStorage.setItem("tasks", JSON.stringify(tasks));
}, [tasks]);

useEffect(() => {
  const saved = JSON.parse(localStorage.getItem("tasks")) || [];
  setTasks(saved);
}, []);
```

---

## **Step 4 – Controlled Form Component**

```jsx
<input
  value={input}
  onChange={(e) => setInput(e.target.value)}
  placeholder="Add a new task..."
/>
```

* Prevent empty submissions
* Clear input after adding task

---

## **Step 5 – Filtering Tasks**

```jsx
const filteredTasks = tasks.filter(task =>
  filter === "active" ? !task.completed :
  filter === "completed" ? task.completed : true
);
```

* Add buttons or select dropdown to switch between filters

---

## **Step 6 – Conditional Rendering**

* Display loading states for API fetches
* Display empty states if no tasks
* Highlight completed tasks

```jsx
{tasks.length === 0 ? <p>No tasks!</p> : <TaskList tasks={filteredTasks} onDelete={deleteTask} />}
```

---

## **Step 7 – Optional Enhancements**

* Add a toggle for task completion
* Animate task addition/removal
* Add form validation
* Use `useCallback` for delete/add functions to optimize performance

---

## **Step 8 – Run & Verify**

```bash
npm run dev
```

* Verify:

  * Tasks load from API
  * Tasks persist after reload
  * Tasks can be added, deleted, and filtered

---

## **Submission**

* Push your final project to GitHub
* Ensure code is modular, readable, and runs without errors

---

## **Day 3 Learning Outcomes**

1. Understand **component extraction** and props
2. Integrate **API data fetching** in React
3. Persist and retrieve state using **localStorage**
4. Implement **controlled components**
5. Use **conditional rendering** for dynamic UI
6. Build a **production-ready React app**

---

This README ensures learners have a **step-by-step, fully actionable guide** to complete their Day 3 lab and finish the full TaskMaster app.

---

