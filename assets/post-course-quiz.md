# **React Crash Course 2025 – Post-Course Quiz**

**Duration:** 30–40 minutes
**Format:** Multiple Choice, True/False, Short Answer, and Coding Snippets

---

## **Part 1 – Multiple Choice (1 point each)**

1. Which hook is used to manage **state** in a functional React component?
   a) `useEffect`
   b) `useState`
   c) `useCallback`
   d) `useMemo`

2. What is the **primary purpose of props** in React?
   a) To store component state
   b) To allow parent-to-child data flow and callbacks
   c) To perform side effects
   d) To persist data in `localStorage`

3. What is the effect of an **empty dependency array `[]`** in `useEffect`?
   a) The effect runs on every render
   b) The effect runs only once on mount
   c) The effect never runs
   d) The effect runs only when state changes

4. Which of the following **improves performance** by avoiding unnecessary re-renders?
   a) `useState`
   b) `useEffect`
   c) `useMemo` and `useCallback`
   d) Inline functions in JSX

5. Why do we use **keys** in lists rendered by React?
   a) To identify elements uniquely for reconciliation
   b) To style list items
   c) To pass props
   d) To persist state

6. Which statement is true about **component extraction**?
   a) It increases code duplication
   b) It allows modular and reusable components
   c) It removes the need for props
   d) It prevents using hooks

---

## **Part 2 – True / False (1 point each)**

7. React enforces a one-way data flow from parent to child.
   True / False

8. `useEffect` can be used to fetch data from an API.
   True / False

9. Mutating state directly is considered best practice in React.
   True / False

10. `localStorage` allows you to persist state across browser reloads.
    True / False

11. `useCallback` memoizes functions, while `useMemo` memoizes values.
    True / False

---

## **Part 3 – Short Answer (2 points each)**

12. Explain why **lifting state up** is important in React applications.

13. Describe how you would **handle errors** when fetching data from an API in `useEffect`.

14. What is the difference between **controlled and uncontrolled components** in React forms?

15. Give two examples of **conditional rendering** in React.

16. Explain one way to **optimize performance** in a React list of components.

---

## **Part 4 – Coding Snippets (3 points each)**

17. **API Fetch & Loading State**
    Write a `useEffect` hook that fetches a list of tasks from `https://jsonplaceholder.typicode.com/todos?_limit=5`, stores them in `tasks` state, and manages a `loading` state variable.

18. **Component Extraction & Props**
    Write a functional React component `TaskItem` that receives a `task` object and an `onDelete` callback via props, and renders the task text with a delete button.

19. **Filter Implementation**
    Write a small code snippet to filter a list of tasks based on a `filter` state variable (`all`, `active`, `completed`) using `useMemo`.

---

## **Part 5 – Bonus (Optional, 2 points)**

20. Describe one **UX improvement** you implemented in TaskMaster Pro and why it is important.

---

### **Answer Key (Trainer Reference)**

**Part 1:** 1-b, 2-b, 3-b, 4-c, 5-a, 6-b
**Part 2:** 7-True, 8-True, 9-False, 10-True, 11-True
**Part 3 / 4 / 5:** Evaluated based on correctness, reasoning, and functional code

---

