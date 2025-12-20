# **React Crash Course 2025 – Day 1 Learner Guide**

**Theme:** Foundations – Environment, JSX, Functional Components, State, and Lists

---

## **Learning Objectives**

By the end of today, you should be able to:

1. Set up a modern React environment using **Vite** and **Node.js**.
2. Understand **declarative UI** vs **imperative DOM manipulation**.
3. Create **functional components** and reuse them.
4. Manage component state with **`useState`**.
5. Render dynamic lists using `.map()` and assign unique `key`s.
6. Handle **user input** and **form events**.
7. Apply basic **CSS styling** to React components.

---

## **1. Setting Up the Environment**

1. **Verify Node.js & npm installation**

```bash
node -v
npm -v
```

2. **Create a new React app with Vite**

```bash
npm create vite@latest notekeeper -- --template react
cd notekeeper
npm install
npm run dev
```

3. Open the app in your browser at the provided URL (usually `http://localhost:5173`)

**Tip:** Keep your terminal and editor side by side for faster feedback.

---

## **2. Understanding React Concepts**

### **2.1 Declarative vs Imperative UI**

**Imperative JS Example:**

```js
document.getElementById("title").innerText = "Hello";
```

**React (Declarative) Example:**

```jsx
<h1>{title}</h1>
```

💡 **Key idea:** You describe *what* the UI should be, not *how* to update it.

---

### **2.2 Virtual DOM & Reconciliation**

* React maintains a lightweight **Virtual DOM**.
* When state changes:

  1. New Virtual DOM is created
  2. React **diffs** old vs new
  3. Only updated nodes are applied to the real DOM

**Benefit:** Efficient, fast updates, even for large apps.

---

### **2.3 One-Way Data Flow**

* Data flows from **parent → child** via **props**
* Child communicates changes via **callback functions**

```jsx
<Child onChange={handleChange} />
```

**Tip:** Avoid changing parent state directly inside child components.

---

## **3. JSX & Functional Components**

### **3.1 JSX Rules**

* Return **one root element** per component
* Use `{ }` for JavaScript expressions
* `className` instead of `class`, `htmlFor` instead of `for`

```jsx
<h1 className="title">{title}</h1>
```

### **3.2 Functional Components**

```jsx
function Note({ content }) {
  return <li>{content}</li>;
}
```

* Accept **props**
* Return **JSX**
* Use **state with hooks** if needed

---

## **4. Managing State with `useState`**

```jsx
import { useState } from "react";

const [notes, setNotes] = useState([]);
```

* Updating state triggers a **re-render**
* **Immutability rule:** Always create a **new array/object** when updating state

```jsx
setNotes([...notes, newNote]); // correct
```

---

## **5. Rendering Lists & Keys**

```jsx
<ul>
  {notes.map(note => (
    <li key={note.id}>{note.content}</li>
  ))}
</ul>
```

* Use **unique `key`** for each list item
* Helps React efficiently update the DOM

---

## **6. Handling Forms & Events**

```jsx
<form onSubmit={handleAddNote}>
  <input value={input} onChange={e => setInput(e.target.value)} />
  <button>Add Note</button>
</form>
```

* Use `onChange` for input
* Use `onSubmit` for form submission
* Use `e.preventDefault()` to prevent page reload

---

## **7. Basic Styling**

* Inline CSS:

```jsx
<h1 style={{ color: "blue" }}>Note Keeper</h1>
```

* External CSS (`App.css`):

```css
.note-list li {
  padding: 8px;
  border-bottom: 1px solid #ccc;
}
```

* Use **className** in JSX to connect styles

---

## **8. Day 1 Lab: Note Keeper App**

**Features to Implement Today:**

1. Display a list of notes
2. Add notes via input form
3. Delete notes from the list
4. Apply basic styling
5. Use functional components (`Note`) and `useState`

**Lab Steps:**

1. Scaffold app with Vite
2. Create `App.jsx` and `Note.jsx` components
3. Implement state and event handlers
4. Render dynamic notes list with keys
5. Style the notes list

---

## **9. Takeaways**

* React is **declarative**, not imperative
* State management is crucial for dynamic apps
* Components should be **modular and reusable**
* Always **use keys** when rendering lists
* Forms and events are handled via props and state

---

## **10. Homework / Practice**

* Add **character count** for each note
* Show **empty state** when no notes exist
* Experiment with **inline vs CSS styles**
* Prepare questions for **Day 2**: API calls & `useEffect`

---

