# **React Crash Course 2025 – Day 3 Learner Guide**

**Theme:** API Integration, Component Patterns & Performance

**Duration:** 6–7 hours

**Prerequisites:**

* Completion of Day 1 & Day 2 labs
* Familiarity with `useState`, `useEffect`, props, and component extraction
* Working React project scaffolded from previous days

---

## **Learning Objectives**

By the end of today, you will be able to:

1. Extract reusable components (`TaskList`, `TaskItem`)
2. Integrate external APIs using `useEffect`
3. Handle **loading, error, and empty states**
4. Persist state using `localStorage`
5. Implement filtering and conditional rendering
6. Optimize performance with `useMemo` and `useCallback`
7. Debug React applications efficiently

---

## **Agenda**

| Time      | Topic                                                    |
| --------- | -------------------------------------------------------- |
| 0:00–0:30 | Recap: Side effects, component extraction, props & state |
| 0:30–1:15 | Advanced Component Patterns                              |
| 1:15–2:15 | API Integration                                          |
| 2:15–2:30 | Break                                                    |
| 2:30–3:15 | State Persistence (`localStorage`)                       |
| 3:15–4:00 | Conditional Rendering & Filtering                        |
| 4:00–4:15 | Break                                                    |
| 4:15–5:00 | Performance Optimization                                 |
| 5:00–5:45 | Debugging & Best Practices                               |
| 5:45–6:30 | Capstone Project Lab                                     |
| 6:30–7:00 | Wrap-up & Q&A                                            |

---

## **Lab Instructions – Step by Step**

### **Part 1 – Component Extraction & Reusability**

**Goal:** Clean up your app by breaking it into smaller components.

**Steps:**

1. In your project, create `TaskList.jsx` and `TaskItem.jsx` under `src/components/`.
2. Move relevant JSX from `App.jsx` to the new components.
3. Pass `tasks` as props to `TaskList` and callbacks (like `handleDelete`) to `TaskItem`.
4. Ensure `App.jsx` still manages state; children should only render UI and trigger callbacks.

**Checkpoint:**

* `App.jsx` is cleaner, smaller, and easier to read.
* Components are reusable.

---

### **Part 2 – API Integration**

**Goal:** Fetch initial tasks from an API using `useEffect`.

**Steps:**

1. Choose an API endpoint (e.g., `https://jsonplaceholder.typicode.com/todos?_limit=5`).
2. Inside `useEffect`, fetch tasks asynchronously and update state.
3. Handle **loading** and **error** states with separate state variables.

**Hints:**

* Use an empty dependency array `[]` to fetch once on mount.
* Wrap fetch in `try/catch`.

**Checkpoint:**

* Tasks appear automatically on page load.
* No console errors or infinite loops.

---

### **Part 3 – State Persistence (`localStorage`)**

**Goal:** Keep tasks across page reloads.

**Steps:**

1. On app load, read tasks from `localStorage`.
2. On task changes, save updated tasks to `localStorage`.

```jsx
useEffect(() => {
  localStorage.setItem('tasks', JSON.stringify(tasks));
}, [tasks]);
```

**Checkpoint:**

* Tasks remain after browser refresh.

---

### **Part 4 – Conditional Rendering & Filters**

**Goal:** Dynamically show different UI states and filter tasks.

**Steps:**

1. Show a loading message while fetching.
2. Show error messages when fetch fails.
3. Show “No tasks” if task list is empty.
4. Add filter buttons: **All**, **Active**, **Completed**.

**Checkpoint:**

* UI reacts appropriately to app state.
* Filtering works correctly.

---

### **Part 5 – Performance Optimization**

**Goal:** Prevent unnecessary re-renders.

**Steps:**

1. Use `useMemo` to memoize filtered task lists.
2. Use `useCallback` to memoize functions passed as props.

```jsx
const filteredTasks = useMemo(() => filterTasks(tasks, filter), [tasks, filter]);
const handleDelete = useCallback((id) => { ... }, [tasks]);
```

**Checkpoint:**

* App renders efficiently.
* No unnecessary re-renders in `TaskList` or `TaskItem`.

---

### **Part 6 – Debugging & Best Practices**

**Goal:** Identify issues and keep code maintainable.

**Steps:**

1. Inspect components and state using **React DevTools**.
2. Console log effects to check execution order.
3. Ensure components are modular and follow one-way data flow.

**Checkpoint:**

* App is stable, clean, and debuggable.

---

## **Capstone Project Deliverables**

By the end of the day, your **TaskMaster Pro app** should:

* Use modular `TaskList` and `TaskItem` components
* Fetch tasks from an API and handle async side effects
* Persist tasks with `localStorage`
* Handle loading, error, and empty states
* Filter tasks dynamically (All / Active / Completed)
* Apply performance optimizations (`useMemo` / `useCallback`)
* Have clean, modular, and maintainable code

---

## **Stretch Challenges**

* Add task completion toggle
* Disable input during API calls
* Highlight completed tasks with CSS
* Add due dates or priorities
* Add animations for task addition/removal

---

## **Tips for Success**

* Break problems into small, manageable tasks
* Test each feature before moving on
* Keep `App.jsx` focused on state management
* Children should only handle rendering and trigger callbacks
* Use DevTools to inspect state and props flow

---

## **Next Steps**

* Explore **state management libraries** (Redux, Zustand) for larger apps
* Extend your TaskMaster app with additional features
* Practice API integration patterns for different endpoints

---

