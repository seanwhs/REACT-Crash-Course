# **React Crash Course 2025 – Day 1 Trainer Guide**

**Theme:** Foundations & Mental Models
**Outcome:** Learners finish Day 1 with a **working React app foundation** (no APIs yet) and the correct mental model.

---

## **Day 1 High-Level Outcomes**

By the end of Day 1, learners should be able to:

* Explain **why React exists** (not just how to use it)
* Describe **declarative UI**, Virtual DOM, and one-way data flow
* Scaffold a React app using **Vite**
* Write **functional components**
* Use **useState** correctly (immutability)
* Render lists with **keys**
* Handle forms and user input
* Produce a **running app** (Note Keeper / Task list foundation)

⚠️ **Trainer rule:**
Do **not** rush hooks. Mental models > syntax.

---

## **Recommended Day 1 Schedule (7 Hours)**

| Time        | Segment                            |
| ----------- | ---------------------------------- |
| 09:00–09:30 | Introduction & Expectations        |
| 09:30–10:30 | React Mental Model                 |
| 10:30–10:45 | Break                              |
| 10:45–11:45 | Tooling: Node, Vite, Project Setup |
| 11:45–12:30 | JSX & Functional Components        |
| 12:30–13:30 | Lunch                              |
| 13:30–14:30 | `useState` Deep Dive               |
| 14:30–15:15 | Lists, Keys & Rendering            |
| 15:15–15:30 | Break                              |
| 15:30–16:45 | Day 1 Lab (Guided)                 |
| 16:45–17:00 | Review & Day 2 Preview             |

---

## **1. Introduction & Framing (09:00–09:30)**

### Trainer Talking Points

* React is **not magic**
* React solves **UI complexity at scale**
* Today = **foundations**
* Day 2 = APIs, effects, architecture
* Day 3 = production patterns, performance

### Set Expectations

Tell learners:

> “If you don’t fully understand `useEffect` today, that’s normal.
> If you don’t understand `useState` today, stop me immediately.”

---

## **2. React Mental Model (09:30–10:30)**

### Core Concepts to Emphasize

#### Declarative vs Imperative

**Key line to repeat:**

> “In React, UI is a function of state.”

Draw this on the board:

```
STATE  →  UI
```

Explain that:

* React re-runs the component function on every state change
* React decides what DOM changes are needed

⚠️ **Common Mistake to Call Out**

* Learners trying to “manually update” the DOM

---

### Virtual DOM & Reconciliation

**Trainer Analogy:**

* Virtual DOM = **blueprint**
* Real DOM = **building**
* React compares blueprints before renovating

**Do NOT:**

* Go deep into algorithm internals
* Mention Fiber scheduling yet

---

### One-Way Data Flow

Emphasize:

* Parents own state
* Children receive data via props
* Children request changes via callbacks

**Ask learners:**

> “Why is two-way data binding dangerous?”

(Expected answer: unpredictable state)

---

## **3. Tooling & Environment (10:45–11:45)**

### Teaching Intent

This section is about **confidence**, not mastery.

### Key Points

* Node.js is required for:

  * npm
  * build tooling
  * dev server
* Vite:

  * instant startup
  * native ES modules
  * fast HMR

### Live Demo (Strongly Recommended)

1. `node -v`
2. `npm create vite@latest`
3. Run dev server
4. Open browser

⚠️ **Trainer Tip**
Walk slowly. Tooling issues cause anxiety.

---

## **4. JSX & Functional Components (11:45–12:30)**

### Teaching Flow

1. Show JSX
2. Explain it is **not HTML**
3. Show JavaScript inside `{}`

### Emphasize Rules

* One root element
* `className`
* Expressions only (no statements)

**Trainer Demo Idea:**
Break JSX on purpose:

* Missing root
* Using `if` directly in JSX

Explain error messages calmly.

---

## **5. `useState` Deep Dive (13:30–14:30)**

### Teaching Intent

This is the **most important topic of Day 1**.

---

### Key Explanation

```js
const [value, setValue] = useState(initialValue);
```

Explain:

* React stores state **outside** the function
* Calling `setValue`:

  * updates state
  * re-runs component
  * triggers Virtual DOM diff

---

### Immutability (Critical)

Write this on the board:

❌ Mutate
✅ Replace

Examples:

```js
tasks.push(newTask);     // WRONG
setTasks([...tasks]);   // RIGHT
```

**Trainer Phrase to Repeat:**

> “React detects changes by reference, not by mutation.”

---

### Common Learner Mistakes

| Mistake                            | Correction              |
| ---------------------------------- | ----------------------- |
| Direct state mutation              | Use spread / new object |
| Expecting state update immediately | Explain async state     |
| Logging state after `setState`     | Explain re-render       |

---

## **6. Lists & Keys (14:30–15:15)**

### Key Teaching Point

Keys are **not for React warnings**
Keys are for **DOM identity**

Explain:

* Keys allow React to match elements between renders
* Index as key = bugs in dynamic lists

**Ask learners:**

> “What happens if I delete the first item?”

---

## **7. Day 1 Lab (15:30–16:45)**

### Trainer Role During Lab

You are:

* Coach
* Debugger
* Encourager

You are **not**:

* Writing code for them
* Racing ahead

---

### Lab Expectations

Learners should:

* Create a React app
* Build:

  * Input field
  * Button
  * List of items
* Add items
* Delete items
* Use components properly

---

### Common Lab Issues & Fixes

| Issue               | Coaching Response            |
| ------------------- | ---------------------------- |
| App not rendering   | Check return JSX             |
| List not updating   | Check immutability           |
| Input not clearing  | Controlled input explanation |
| Button reloads page | `preventDefault()`           |

---

## **8. Wrap-Up & Day 2 Preview (16:45–17:00)**

### Review Questions to Ask

* What causes a re-render?
* Why must state be immutable?
* What is the Virtual DOM?
* Why do we need keys?

---

### Day 2 Teaser

Tell learners:

> “Tomorrow, we connect this app to the real world:
> APIs, side effects, component architecture.”

---

## **Trainer Success Checklist (Day 1)**

✅ Learners can explain declarative UI
✅ Learners can scaffold a React app
✅ Learners use `useState` correctly
✅ Learners understand immutability
✅ Learners finish with a working app

If these are met, **Day 1 is a success**.

---
