# **React Crash Course 2025 Lab Workbook**

**Objective:** Provide hands-on exercises that reinforce React concepts, component patterns, hooks, API integration, state management, and performance best practices.

**Duration:** 3 Days (Approx. 6–7 hours per day)

**Prerequisites:**

* Basic knowledge of HTML, CSS, and JavaScript
* Familiarity with ES6+ syntax (`let/const`, arrow functions, destructuring)
* Node.js and npm installed

---

## **Day 1 Lab – Foundations & Tooling**

### **Learning Objectives**

By the end of Day 1, learners will be able to:

* Scaffold a React project using Vite
* Understand declarative vs imperative UI
* Explain Virtual DOM & reconciliation
* Implement one-way data flow using props
* Organize project structure

### **Lab Tasks**

#### **Task 1 – Verify Node.js & npm**

1. Open terminal
2. Run:

```bash
node -v
npm -v
```

3. Confirm that Node.js and npm are installed

#### **Task 2 – Scaffold React Project**

1. Run:

```bash
npm create vite@latest taskmaster-app -- --template react
cd taskmaster-app
npm install
npm run dev
```

2. Open project in VSCode

#### **Task 3 – Explore Project Structure**

* Identify:

  * `src/main.jsx` – entry point
  * `src/App.jsx` – root component
  * `src/components/` – folder for reusable components
  * `src/App.css` – styles

#### **Task 4 – Declarative vs Imperative**

* Write an **imperative DOM update** in `index.html`
* Write equivalent **React declarative code** in `App.jsx`

#### **Checkpoint**

* Project runs without errors
* React app displays “Hello, React!” using JSX

---

## **Day 2 Lab – Components & Hooks**

### **Learning Objectives**

By the end of Day 2, learners will be able to:

* Use `useState` and `useEffect`
* Extract reusable components
* Pass props and callbacks
* Fetch data from an API
* Handle loading, error, and empty states

### **Lab Tasks**

#### **Task 1 – Add Local State**

1. In `App.jsx`, create `tasks` state using `useState`
2. Implement `addTask` and `deleteTask` functions

#### **Task 2 – Extract Components**

1. Create `TaskList.jsx` and `TaskItem.jsx` in `components/`
2. Move JSX logic for tasks into these components
3. Pass `tasks` and callbacks via props

#### **Task 3 – Fetch API Data**

1. Use `useEffect` to fetch tasks from `https://jsonplaceholder.typicode.com/todos?_limit=5`
2. Handle async calls with `try/catch`
3. Manage `loading` and `error` states

#### **Task 4 – Conditional Rendering**

* Show different UI for:

  * Loading
  * Error
  * Empty list
  * Data available

#### **Checkpoint**

* Tasks load automatically
* Components render correctly
* Props flow is unidirectional
* No console errors

---

## **Day 3 Lab – API Integration, Patterns & Performance**

### **Learning Objectives**

By the end of Day 3, learners will be able to:

* Persist state using `localStorage`
* Implement filtering and conditional rendering
* Apply `useMemo` and `useCallback` for performance
* Debug React applications efficiently

### **Lab Tasks**

#### **Task 1 – Persist State**

1. Read tasks from `localStorage` on app load
2. Write updated tasks to `localStorage` on changes

#### **Task 2 – Implement Filters**

1. Create a `filter` state (`all`, `active`, `completed`)
2. Filter tasks based on selection using `useMemo`

#### **Task 3 – Performance Optimization**

1. Wrap callbacks passed to children in `useCallback`
2. Memoize filtered task lists using `useMemo`
3. Confirm that unnecessary re-renders are avoided

#### **Task 4 – Capstone Integration**

* Combine all previous steps to finalize **TaskMaster Pro**
* Ensure:

  * Modular components
  * API integration
  * State persistence
  * Conditional rendering
  * Filtering
  * Performance optimizations

#### **Checkpoint**

* App works correctly after reloads
* Filtering and conditional rendering are functional
* App performs efficiently without unnecessary renders

---

## **Reflection Questions (All Days)**

1. How does **one-way data flow** help in debugging?
2. Why is it important to **extract components**?
3. How does `useEffect` prevent direct DOM manipulation issues?
4. How does `localStorage` improve user experience?
5. Describe one **performance optimization** you implemented and why.

---

## **Stretch Challenges**

* Add task completion toggle
* Highlight completed tasks with CSS
* Disable input while loading
* Add animations for adding/removing tasks
* Add due dates or priority levels

---

## **Deliverables**

By the end of Day 3, learners should submit or demonstrate:

* Functional **TaskMaster Pro app**
* Reusable `TaskList` and `TaskItem` components
* API data fetching with loading/error states
* Persistent state via `localStorage`
* Filter buttons with `useMemo` optimization
* Optimized app performance using `useCallback`
* Clean, maintainable, modular code

---

## **Assessment Criteria**

| Area        | Expected Outcome                                |
| ----------- | ----------------------------------------------- |
| `useEffect` | Correctly implemented for API calls             |
| State       | Managed immutably and persists across reloads   |
| Components  | Modular, reusable, and props-driven             |
| API Fetch   | Handles loading & errors gracefully             |
| Filtering   | Filters tasks correctly based on state          |
| Performance | Uses `useMemo` / `useCallback` effectively      |
| UX          | Clear feedback for loading, empty, error states |


