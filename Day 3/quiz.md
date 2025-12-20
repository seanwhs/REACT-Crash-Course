# **React Crash Course 2025 – Day 3 Quiz**

**Duration:** 20–30 minutes
**Format:** Mix of multiple choice, true/false, short answer, and coding snippets

---

## **Part 1 – Multiple Choice (1 point each)**

1. Which hook is used to handle **side effects** such as API calls?
   a) `useState`
   b) `useEffect`
   c) `useCallback`
   d) `useMemo`

2. When fetching data from an API inside `useEffect`, what should you include to **avoid infinite re-renders**?
   a) `console.log()`
   b) Dependency array
   c) Inline JSX fetch
   d) `setTimeout()`

3. In React, **child components should…**
   a) Directly update parent state
   b) Modify props to change parent data
   c) Use callbacks passed via props to trigger changes
   d) Manage all state independently

4. What is the main purpose of using `useMemo`?
   a) Trigger side effects
   b) Memoize expensive calculations to avoid unnecessary re-renders
   c) Replace `useState`
   d) Persist data to `localStorage`

5. Why do we use **`localStorage`** in React apps?
   a) To fetch data from APIs
   b) To persist state across browser reloads
   c) To style components
   d) To optimize rendering

---

## **Part 2 – True / False (1 point each)**

6. `useCallback` is used to memoize functions to prevent unnecessary re-renders.
   True / False

7. Conditional rendering in React can be used to show a loading spinner only when data is being fetched.
   True / False

8. It is safe to mutate state objects directly in child components as long as you pass them via props.
   True / False

9. React DevTools can help debug props, state, and component hierarchy.
   True / False

10. An empty dependency array `[]` in `useEffect` ensures the effect runs only once on mount.
    True / False

---

## **Part 3 – Short Answer (2 points each)**

11. Explain the difference between `useMemo` and `useCallback`.

12. Describe how you would implement a **filter for tasks** (All, Active, Completed) in your TaskMaster app.

13. What are the steps to **persist tasks in localStorage** and retrieve them when the app loads?

---

## **Part 4 – Coding Snippets (3 points each)**

14. **API Fetch & Loading State**
    Write a `useEffect` hook that fetches tasks from `https://jsonplaceholder.typicode.com/todos?_limit=5`, stores them in `tasks` state, and uses a `loading` state variable to indicate loading.

15. **Component Extraction**
    Given a parent `App.jsx` managing `tasks`, write a **functional child component** `TaskItem` that receives a `task` and an `onDelete` callback via props and renders the task with a delete button.

---

## **Part 5 – Bonus (Optional, 2 points)**

16. Explain one **performance optimization** you implemented or could implement in TaskMaster Pro and why it is important.

---

### **Answer Key (Trainer Reference)**

**Part 1:** 1-b, 2-b, 3-c, 4-b, 5-b
**Part 2:** 6-True, 7-True, 8-False, 9-True, 10-True
**Part 3 / 4 / 5:** Evaluated based on correctness of explanation and functional code

---


