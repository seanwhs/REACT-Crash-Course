# **React Crash Course 2025 — Day 2 Trainer Guide**

## **Day 2 Objective**

By the end of Day 2, learners must be able to:

✔ Explain what a **side effect** is in React
✔ Use `useEffect` correctly without infinite loops
✔ Fetch and render API data safely
✔ Handle loading and error states
✔ Refactor a growing component into **clean child components**
✔ Explain **why** React enforces one-way data flow

If learners can *do these things without copy-paste*, Day 2 is successful.

---

## **Trainer Mindset for Day 2**

Day 1 was about **confidence and foundations**.
Day 2 is about **discipline and correctness**.

Learners will:

• Overuse `useEffect`
• Break apps with infinite loops
• Struggle with async mental models
• Want to “just make it work”

Your role is to **slow them down and enforce patterns**.

---

## **Suggested Day 2 Timeline (7–8 Hours)**

| Time      | Activity                             |
| --------- | ------------------------------------ |
| 0:00–0:30 | Day 1 recap + mental model refresh   |
| 0:30–1:15 | Side effects & `useEffect` deep dive |
| 1:15–2:15 | API fetching patterns                |
| 2:15–2:30 | Break                                |
| 2:30–3:30 | Loading & error states               |
| 3:30–4:30 | Component extraction                 |
| 4:30–5:30 | Props & callback patterns            |
| 5:30–6:30 | Guided lab                           |
| 6:30–7:00 | Review & Q&A                         |

---

## **1. Day 1 Recap (Trainer Notes)**

### **Ask Learners:**

• What causes a React component to re-render?
• Why must state updates be immutable?
• What does React do when state changes?

### **Expected Answers**

• State change
• New reference triggers diff
• Virtual DOM reconciliation

⚠️ If learners struggle here, **do not proceed**.

---

## **2. Teaching Side Effects (Critical Section)**

### **Key Message**

> “Rendering must be pure. Side effects must be isolated.”

Write on the board:

```
Render = describe UI
Effect = interact with outside world
```

---

### **Whiteboard Prompt**

Ask:

> “Is `console.log` a side effect?”

Answer: Yes — but harmless.

Use this to transition into **API calls as dangerous side effects**.

---

## **3. Teaching `useEffect` Without Fear**

### **Rule You Must Enforce**

> Effects do NOT run *during* render.
> They run *after* render.

Draw this flow:

```
Render → Paint → useEffect
```

---

### **Dependency Array Drill**

Ask learners to predict behavior:

```js
useEffect(() => {}, []);
useEffect(() => {}, [count]);
useEffect(() => {});
```

Make them answer **out loud**.

---

## **4. Infinite Loop Demonstration (Highly Recommended)**

Live-code this mistake:

```js
useEffect(() => {
  setCount(count + 1);
});
```

Let the app crash.

Then ask:

> “Why did this happen?”

Only proceed when they can explain **render → effect → render loop**.

---

## **5. API Fetching Instruction**

### **Non-Negotiable Rules**

✔ Fetch inside `useEffect`
✔ Use async function inside effect
✔ Handle loading state
✔ Handle error state

---

### **Explain This Clearly**

React does **not care** about async.
React cares about **when state changes**.

---

### **Trainer Tip**

Avoid Axios at this stage.
Use `fetch` to reduce abstraction noise.

---

## **6. Loading & Error States (UX Discipline)**

### **Key Teaching Point**

> “If your app doesn’t explain what it’s doing, users think it’s broken.”

Show examples of:

• Blank screens
• Flashing content
• Unhandled errors

Make learners uncomfortable with these.

---

## **7. Component Extraction (Architecture Focus)**

### **Rule to Teach**

> One component = one responsibility.

If learners resist extraction:

• Ask them to explain the component aloud
• Point out mixed responsibilities

---

### **Whiteboard Exercise**

Draw:

```
App
 ├── TaskList
 │    └── TaskItem
```

Then ask:

> “Who owns the state?”

Correct answer: `App`.

---

## **8. Props & Callback Discipline**

### **Repeat This Often**

> Children never modify parent state directly.

Live-code:

```js
onDelete={() => deleteTask(id)}
```

Explain:

• Parent owns logic
• Child only triggers intent

---

## **9. Lab Facilitation Strategy**

### **Do NOT:**

❌ Write full solutions
❌ Fix errors immediately
❌ Debug for them

### **DO:**

✔ Ask what state is wrong
✔ Ask when effect runs
✔ Ask what triggered re-render

---

## **10. Common Learner Mistakes (Watch For These)**

| Mistake             | How to Correct               |
| ------------------- | ---------------------------- |
| Infinite loops      | Dependency array explanation |
| Mutating state      | Spread operator demo         |
| Fetch in JSX        | Explain render purity        |
| Props misuse        | Reinforce ownership          |
| Overusing useEffect | Ask “Is this a side effect?” |

---

## **11. End-of-Day Evaluation Criteria**

A learner passes Day 2 if they can:

✔ Explain when `useEffect` runs
✔ Fetch data without infinite loops
✔ Refactor App into child components
✔ Pass props and callbacks correctly
✔ Debug basic React warnings

If they cannot explain it, they don’t own it.

---

## **12. Instructor Closing Script (Optional)**

> “Today you stopped writing toy React.
> You’re now writing React the way production teams do.”

Preview Day 3:

• Persistence
• Performance
• Production mindset

---

## **Trainer Prep Checklist**

Before Day 2:

✔ Verify API endpoint works
✔ Prepare broken examples
✔ Have infinite loop demo ready
✔ Ensure DevTools installed

---

