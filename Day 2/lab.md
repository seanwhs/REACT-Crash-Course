# **Day 2 Lab — APIs, Side Effects & Component Architecture**

## **Lab Objective**

By the end of this lab, learners will:

• Fetch data from an external API
• Use `useEffect` correctly
• Handle loading and error states
• Extract components
• Pass data and callbacks via props
• Structure a React app professionally

---

## **Starting Point (From Day 1)**

You should already have:

• A Vite + React project
• A working task list UI
• Ability to add and delete tasks
• State managed with `useState`

⚠️ **Do not copy from slides or tutorial code**
This lab requires **independent implementation**

---

## **Lab Part 1 — Add API Data on App Load**

### **Goal**

Load initial tasks from an API when the app starts.

---

### **Requirements**

1. Choose an API endpoint
   Example (suggested but not required):

```
https://jsonplaceholder.typicode.com/todos?_limit=5
```

2. Fetch tasks **once when the app loads**
3. Convert API data into your app’s task format
4. Store results in React state

---

### **Constraints**

• Fetch must happen inside `useEffect`
• Do NOT fetch inside JSX
• Use async/await
• Avoid infinite re-renders

---

### **Hints**

• Use an empty dependency array `[]`
• Store fetched data using `setState`
• Map API fields into your own structure

---

### **Checkpoint**

✔ Tasks appear automatically on page load
✔ No console errors
✔ No infinite loops

---

## **Lab Part 2 — Add Loading State**

### **Goal**

Display feedback while API data is loading.

---

### **Requirements**

1. Create a `loading` state variable
2. Show a loading message while fetching
3. Hide the message once data is loaded

---

### **Expected Behavior**

• Page loads
• "Loading..." appears
• Tasks appear
• Loading message disappears

---

### **Hints**

• Set loading to `true` initially
• Set to `false` after fetch completes
• Use conditional rendering

---

### **Checkpoint**

✔ Loading message works correctly
✔ No flashing or infinite loading

---

## **Lab Part 3 — Handle API Errors**

### **Goal**

Gracefully handle fetch failures.

---

### **Requirements**

1. Add an `error` state
2. Catch fetch errors
3. Display an error message if fetch fails

---

### **Expected Behavior**

• App does not crash
• User sees meaningful feedback

---

### **Hints**

• Wrap fetch logic in `try/catch`
• Set error state inside `catch`
• Conditionally render error message

---

### **Checkpoint**

✔ Error message displays correctly
✔ App still runs

---

## **Lab Part 4 — Extract Components**

### **Goal**

Split UI into smaller components.

---

### **Required Components**

• `TaskList`
• `TaskItem`

---

### **Rules**

• App component owns all state
• Child components receive data via props
• Child components do NOT modify state directly

---

### **Hints**

• Pass tasks as props
• Pass delete handlers as props
• Use destructuring in component parameters

---

### **Checkpoint**

✔ App.jsx is clean and readable
✔ Components are reusable
✔ Props flow correctly

---

## **Lab Part 5 — Props & Event Handling**

### **Goal**

Use props to trigger parent state updates.

---

### **Requirements**

1. `TaskItem` displays task text
2. `TaskItem` triggers delete via props
3. Parent handles actual deletion

---

### **Hints**

• Child receives a callback function
• Child calls callback with task ID

---

### **Checkpoint**

✔ Clicking delete removes correct task
✔ No direct state mutation in children

---

## **Lab Part 6 — Improve UX with Conditional Rendering**

### **Goal**

Make UI respond to app state.

---

### **Requirements**

• Show empty message if no tasks
• Show loading message when fetching
• Show error message if fetch fails

---

### **UI States to Handle**

• Loading
• Error
• Empty
• Data available

---

### **Checkpoint**

✔ UI always matches app state
✔ No blank screens

---

## **Stretch Challenges (Optional but Encouraged)**

⭐ Add task completion toggle
⭐ Disable input while loading
⭐ Highlight completed tasks
⭐ Add basic CSS styling
⭐ Console-log effect execution order

---

## **Deliverables**

By the end of Day 2 Lab, learners should have:

✔ A working React app
✔ API-driven initial data
✔ Proper use of `useEffect`
✔ Loading and error handling
✔ Extracted components
✔ Clean props-based data flow

---

## **Assessment Criteria**

| Area       | Expected                 |
| ---------- | ------------------------ |
| useEffect  | Correct usage            |
| API Fetch  | No render blocking       |
| State      | Immutable updates        |
| Components | Modular                  |
| Props      | One-way data flow        |
| UX         | Loading & errors handled |

---

## **Instructor Notes**

• Do NOT provide full solutions
• Ask learners to explain:
– Why `useEffect` is needed
– Why dependencies matter
– Why state lives in App

---

## **End-of-Day Outcome**

Learners now understand:

• Side effects in React
• API integration
• Component architecture
• Real-world app structure

➡️ **Day 3 will finalize the app for production**

---
