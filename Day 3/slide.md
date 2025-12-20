# **Slide 1 – React Crash Course 2025: Day 3**

**Title:** API Integration, Component Patterns & Performance

**Content:**

* **Learning Objectives:**

  * Fetch and manage external data with `useEffect`
  * Extract reusable components (`TaskList`, `TaskItem`)
  * Implement props and callbacks for controlled data flow
  * Persist state with `localStorage`
  * Apply filters and conditional rendering
  * Optimize performance with `useMemo` and `useCallback`

*(Visual: roadmap icon showing “Data → Components → Persistence → Optimization”)*

---

# **Slide 2 – Component Extraction & Reusability**

**Content:**

* Break large UI into smaller components
* Example:

```jsx
<TaskList tasks={tasks} onDelete={handleDelete} />
<TaskItem task={task} onDelete={onDelete} />
```

**Rules:**

* Parent owns state
* Child receives data via props
* Child triggers changes through callbacks

*(Visual: parent-child diagram with arrows showing props & callbacks)*

---

# **Slide 3 – API Integration with useEffect**

**Content:**

* Fetch data from external APIs after component mounts
* Handle loading and error states
* Example:

```jsx
useEffect(() => {
  fetchTasks();
}, []);
```

* Never fetch directly in render
* Use async/await inside `useEffect`

*(Visual: async fetch → setState → render)*

---

# **Slide 4 – State Persistence with localStorage**

**Content:**

* Persist user data across page reloads
* Example:

```jsx
useEffect(() => {
  localStorage.setItem('tasks', JSON.stringify(tasks));
}, [tasks]);
```

* Retrieve on app start:

```jsx
const savedTasks = JSON.parse(localStorage.getItem('tasks')) || [];
```

*(Visual: browser storage icon with arrows to state)*

---

# **Slide 5 – Conditional Rendering & Filters**

**Content:**

* Show different UI based on state:

```jsx
{loading && <p>Loading...</p>}
{error && <p>Error fetching tasks</p>}
{tasks.length === 0 && <p>No tasks found</p>}
```

* Filter tasks dynamically (All / Active / Completed)
* Improve UX by highlighting completed tasks

*(Visual: filter dropdown with task list states)*

---

# **Slide 6 – Performance Optimization**

**Content:**

* Avoid unnecessary re-renders:

  * `useMemo` – memoize expensive calculations
  * `useCallback` – memoize functions passed as props

```jsx
const filteredTasks = useMemo(() => filterTasks(tasks, filter), [tasks, filter]);
const handleDelete = useCallback((id) => { ... }, [tasks]);
```

* Use **keys** correctly in lists
* Keep state immutable

*(Visual: chart showing re-rendering reduction)*

---

# **Slide 7 – Debugging & Best Practices**

**Content:**

* React DevTools for inspecting components & state
* Console logging side effects to verify order
* Keep components **modular and readable**
* Avoid direct DOM manipulation

*(Visual: React DevTools screenshot or icon)*

---

# **Slide 8 – Capstone Project: TaskMaster Pro – API Edition**

**Content:**

* Features:

  * Add, delete, and complete tasks
  * Fetch tasks from API
  * Persist tasks via `localStorage`
  * Filter tasks dynamically
  * Reusable components

* Learning Outcomes:

  * Build production-ready React apps
  * Apply advanced patterns & performance tips
  * Debug and maintain app efficiently

*(Visual: screenshot/mockup of final app)*

---

# **Slide 9 – Day 3 Key Takeaways**

**Content:**

* Modular component architecture is critical
* `useEffect` manages side effects safely
* `localStorage` persists important state
* Conditional rendering improves UX
* `useMemo` & `useCallback` optimize performance
* Debugging and DevTools keep apps maintainable

*(Visual: checklist or icons for each takeaway)*

---

# **Slide 10 – Next Steps**

**Content:**

* Review Day 3 Lab exercises
* Extend app with additional features or filters
* Explore state management libraries for larger apps (Redux, Zustand)
* Practice API integration and side-effect management

*(Visual: roadmap arrow to “Advanced React Topics”)*

---


Do you want me to do that next?
