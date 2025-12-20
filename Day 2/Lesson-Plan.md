# **Day 2 Lesson Plan — APIs, Side Effects & Component Architecture**

**Course:** React Crash Course 2025
**Day:** 2 of 3
**Duration:** ~6.5 hours (excluding breaks)
**Outcome:** Learners integrate APIs, understand `useEffect`, and refactor into clean components.

---

## **Day 2 Learning Objectives**

By the end of Day 2, learners will be able to:

• Explain what side effects are in React
• Correctly use `useEffect`
• Fetch data from an external API
• Handle loading and error states
• Extract components
• Pass data and callbacks via props
• Architect a React app using best practices

---

## **Day 2 Schedule Overview**

| Time          | Topic                              |
| ------------- | ---------------------------------- |
| 09:00 – 09:30 | Day 1 recap + mental model refresh |
| 09:30 – 10:30 | Side effects & `useEffect`         |
| 10:30 – 10:45 | Break                              |
| 10:45 – 11:45 | API integration                    |
| 11:45 – 12:30 | Loading, error states & UX         |
| 12:30 – 13:30 | Lunch                              |
| 13:30 – 14:45 | Component extraction & props       |
| 14:45 – 15:00 | Break                              |
| 15:00 – 16:30 | Guided Lab (Day 2 Lab)             |
| 16:30 – 17:00 | Review, Q&A, Day 3 preview         |

---

## **Session 1 — Day 1 Recap & Context Setting (30 mins)**

### **Trainer Goals**

• Re-anchor React mental model
• Identify gaps before introducing APIs

---

### **Key Topics to Review**

• Declarative UI
• State → UI relationship
• Immutability
• One-way data flow

---

### **Trainer Activity**

Ask learners:

• “What triggers a re-render in React?”
• “Why can’t we fetch data directly inside JSX?”
• “Who should own state — parent or child?”

---

### **Checkpoint**

✔ Learners can explain `useState`
✔ Learners understand state ownership

---

## **Session 2 — Side Effects & `useEffect` (60 mins)**

### **Concepts Introduced**

**What is a Side Effect?**

Any interaction with the outside world:

• API calls
• Timers
• Logging
• Local storage

---

### **Why `useEffect` Exists**

• React rendering must be pure
• Side effects must be isolated
• Prevent unpredictable behavior

---

### **`useEffect` Anatomy**

```js
useEffect(() => {
  // side effect logic
}, [dependencies]);
```

---

### **Dependency Array Mental Model**

| Dependency | Behavior                |
| ---------- | ----------------------- |
| none       | Runs on every render    |
| `[]`       | Runs once on mount      |
| `[value]`  | Runs when value changes |

---

### **Trainer Demo (Live Coding)**

• Show infinite loop example
• Fix it by adding dependencies
• Console log effect execution

---

### **Common Pitfalls to Highlight**

⚠️ Missing dependency array
⚠️ Updating state inside effect without guard
⚠️ Fetching data during render

---

### **Checkpoint**

✔ Learners understand effect lifecycle
✔ Learners can explain infinite loops

---

## **Session 3 — API Integration (60 mins)**

### **Core Concepts**

• Fetching data asynchronously
• Async / await inside `useEffect`
• Mapping API data into app state

---

### **Trainer Demo**

1. Show raw API response
2. Explain why transformation is needed
3. Map API fields → app fields

---

### **Error Handling**

• Network failure
• Invalid response
• Graceful UI fallback

---

### **Best Practices**

• Use `try/catch`
• Keep fetch logic readable
• Avoid side effects in render

---

### **Checkpoint**

✔ Learners can fetch API data
✔ Learners store data in state

---

## **Session 4 — Loading & Error UX (45 mins)**

### **Concepts**

• Loading is state
• Errors are state
• UI must reflect application state

---

### **Trainer Demo**

• Add loading spinner
• Add error message
• Conditional rendering patterns

---

### **UX Patterns to Emphasize**

• Never leave user guessing
• Fail gracefully
• Avoid blank screens

---

### **Checkpoint**

✔ App shows correct UI for each state

---

## **Session 5 — Component Extraction & Props (75 mins)**

### **Why Extract Components?**

• Readability
• Reusability
• Separation of concerns

---

### **Rules of Props**

• Read-only
• One-way
• Parent owns state

---

### **Trainer Demo**

• Break App into:
– `TaskList`
– `TaskItem`

• Move rendering logic into children
• Pass callbacks for deletion

---

### **Anti-Patterns to Call Out**

⚠️ Child mutating parent state
⚠️ Passing entire state unnecessarily
⚠️ Deep prop drilling

---

### **Checkpoint**

✔ App is modular
✔ Props flow is clean

---

## **Session 6 — Guided Lab (90 mins)**

### **Lab Scope**

Learners implement:

• API fetch
• `useEffect`
• Loading + error handling
• Component extraction

---

### **Trainer Role**

• Circulate
• Ask “why” questions
• Debug misconceptions

---

### **Key Questions to Ask Learners**

• Why is fetch inside `useEffect`?
• Why does App own the state?
• Why do children use callbacks?

---

### **Checkpoint**

✔ Most learners complete core lab
✔ App runs without errors

---

## **Session 7 — Review & Day 3 Preview (30 mins)**

### **Recap**

• Side effects
• APIs
• Components
• Props

---

### **Common Issues Review**

• Infinite effects
• Missing keys
• Incorrect dependency arrays

---

### **Preview Day 3**

• App persistence
• Advanced hooks
• Performance
• Production patterns

---

## **Day 2 Instructor Checklist**

✔ Learners used `useEffect` correctly
✔ API calls isolated
✔ Components extracted
✔ No direct state mutation
✔ App still works end-to-end

---

## **End-of-Day Outcome**

By end of Day 2, learners have:

• A working API-driven React app
• Proper side-effect handling
• Clean component architecture

➡️ **Day 3 will harden the app for production**

---
