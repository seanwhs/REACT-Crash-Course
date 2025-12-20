# **React Crash Course 2025**

Welcome to **React Crash Course 2025** – a high-density, engineer-focused course designed to teach React from the ground up. This course covers architecture, modern tooling, hooks, state management, API integration, component patterns, and building a production-ready application.

---

## **Course Overview**

This course is structured for **3 days of intensive training**, covering:

1. **Day 1 – Core React & Tooling**

   * Declarative vs Imperative UI
   * Virtual DOM & Reconciliation
   * One-way data flow and props
   * Modern tooling with Vite, Node.js, and npm
   * Project scaffolding & directory structure

2. **Day 2 – Components & Hooks**

   * JSX syntax rules
   * Functional components
   * State management with `useState`
   * Side effects with `useEffect`
   * Building TaskMaster Pro – a fully-featured task manager
   * Event handling, conditional rendering, and list keys

3. **Day 3 – API Integration, Component Patterns & Performance**

   * Fetching data from APIs
   * Component extraction (`TaskList`, `TaskItem`)
   * Props for controlled data flow
   * LocalStorage persistence
   * Filtering, conditional rendering, and UX enhancements
   * Performance optimization (`useMemo`, `useCallback`)
   * Debugging best practices

---

## **Prerequisites**

* Basic knowledge of **HTML, CSS, and JavaScript**
* Familiarity with **ES6+ syntax** (arrow functions, `let/const`, template literals, destructuring)
* Node.js installed (LTS recommended)
* npm (comes with Node.js)
* Code editor (VSCode recommended)
* Web browser (Chrome, Edge, or Firefox)

---

## **Getting Started**

1. **Verify Node.js & npm**

```bash
node -v
npm -v
```

2. **Scaffold React Project using Vite**

```bash
npm create vite@latest taskmaster-app -- --template react
cd taskmaster-app
npm install
npm run dev
```

3. **Directory Layout**

```
src/
 ├─ main.jsx      # entry point
 ├─ App.jsx       # root component
 ├─ components/   # reusable UI components
 ├─ App.css       # styles
```

---

## **Project Structure**

* `src/main.jsx` – React entry point
* `src/App.jsx` – Root component containing state and main logic
* `src/components/` – Modular and reusable components (`TaskItem`, `TaskList`, etc.)
* `src/App.css` – Application styles

---

## **Key Concepts Covered**

* **Declarative UI & Virtual DOM** – Efficient updates with minimal DOM manipulation
* **One-way Data Flow** – Predictable state updates with props and callbacks
* **Functional Components & Hooks** – `useState`, `useEffect` for state and side effects
* **Immutability & List Keys** – Essential for efficient re-rendering
* **API Integration** – Fetching data and handling side effects
* **Component Extraction** – Modular, reusable, testable components
* **LocalStorage Persistence** – Maintain state across sessions
* **Conditional Rendering & UX Patterns**
* **Performance & Debugging** – `useMemo`, `useCallback`, React DevTools

---

## **Capstone Project: TaskMaster Pro – API Edition**

* **Features:**

  * Add, delete, and mark tasks complete
  * Fetch tasks from API
  * Persist tasks with LocalStorage
  * Filter tasks (all, active, completed)
  * Modular components for scalability

* **Learning Outcomes:**

  * Build production-ready React apps
  * Manage state, props, and side effects efficiently
  * Apply modern best practices in React development

---

## **Additional Resources**

* [React Official Docs](https://reactjs.org/)
* [Vite Documentation](https://vitejs.dev/)
* [MDN JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
* [JSONPlaceholder API](https://jsonplaceholder.typicode.com/)

---

## **License**

This course content is licensed under the **MIT License** – free to use and adapt for personal or training purposes.

---

