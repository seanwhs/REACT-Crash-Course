# **Slide 1 – React Crash Course 2025: Day 2**

**Title:** Components, Hooks & API Integration

**Content:**

* **Learning Objectives:**

  * Understand and use **side effects** in React
  * Use `useEffect` correctly with dependency arrays
  * Fetch data safely from APIs
  * Handle **loading, error, and empty states**
  * Extract and compose components
  * Apply props for communication
  * Understand **state ownership & lifting state**

*(Visual: roadmap icon showing “State → Effects → Components → Props”)*

---

# **Slide 2 – Side Effects in React**

**Content:**

* React components should stay **pure** during rendering
* Side effects are anything that:

  * Talks to the outside world
  * Changes something outside render
  * Runs asynchronously

**Examples:**

* Fetching data
* Reading from localStorage
* Subscribing to events
* Logging

*(Visual: external world icon → React component)*

---

# **Slide 3 – `useEffect` Mental Model**

**Content:**

* Run code **after render**
* Dependency array controls **when it runs**

```jsx
useEffect(() => {
  // side effect
}, []);
```

* Empty array → run once on mount
* Dependency changes → re-run effect
* Avoid infinite loops

*(Visual: timeline showing render → useEffect → update)*

---

# **Slide 4 – Fetching Data from APIs**

**Content:**

* Fetch inside `useEffect`
* Use async/await
* Handle loading and errors

```jsx
useEffect(() => {
  async function fetchTasks() {
    const res = await fetch(url);
    const data = await res.json();
    setTasks(data);
  }
  fetchTasks();
}, []);
```

*(Visual: API → async fetch → state → render)*

---

# **Slide 5 – Loading, Error & Empty States**

**Content:**

* Never assume data exists
* Conditional rendering for better UX:

```jsx
{loading && <p>Loading...</p>}
{error && <p>Error!</p>}
{tasks.length === 0 && <p>No tasks</p>}
```

* Improves stability and debuggability

*(Visual: different UI states represented as cards)*

---

# **Slide 6 – Component Extraction**

**Content:**

* Split large components into smaller, reusable ones
* Day 2 components:

  * `TaskList`
  * `TaskItem`

**Rules:**

* Parent owns state
* Child receives data via props
* Child triggers changes via callbacks

*(Visual: parent-child diagram with arrows showing props & callbacks)*

---

# **Slide 7 – Props & Data Flow**

**Content:**

* Props are **read-only**
* Parent → Child = data
* Child → Parent = callbacks

```jsx
<TaskItem task={task} onDelete={handleDelete} />
```

* Ensures predictable updates

*(Visual: arrows showing parent → child & child → parent)*

---

# **Slide 8 – State Ownership & Lifting State**

**Content:**

* Key questions:

  * Who owns the data?
  * Who modifies it?
  * Who just displays it?

* Keep state **high enough**

* Pass behavior downward via props

* Avoid prop drilling when possible

*(Visual: hierarchical diagram of components with state at top)*

---

# **Slide 9 – Day 2 Lab Overview**

**Content:**

* Fetch API data into your app
* Show loading and error messages
* Extract components (`TaskList`, `TaskItem`)
* Pass data and callbacks via props
* Handle empty states
* Clean up App component for readability

*(Visual: task list with API integration arrows)*

---

# **Slide 10 – Common Mistakes Addressed**

**Content:**

* ❌ Fetching in render
* ❌ Missing dependency arrays
* ❌ Infinite `useEffect` loops
* ❌ Overloading App component
* ❌ Mutating state from children
* ❌ Passing entire state unnecessarily

*(Visual: warning icons with code snippets)*

---

# **Slide 11 – Day 2 Key Takeaways**

**Content:**

* `useEffect` manages side effects safely
* API integration must handle loading & errors
* Extract components for modular code
* Props enable one-way data flow
* State ownership matters for predictable updates
* Conditional rendering improves UX

*(Visual: checklist or icons representing each takeaway)*

---

# **Slide 12 – How Day 2 Connects to Day 3**

**Content:**

* Day 2 builds foundation for **scaling the app**
* Day 3 adds:

  * State persistence (`localStorage`)
  * Performance optimization (`useMemo`, `useCallback`)
  * Final UX polish
  * Production-ready architecture

*(Visual: arrow from Day 2 → Day 3)*

---
