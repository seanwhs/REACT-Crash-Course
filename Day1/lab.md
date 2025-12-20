# **Day 1 Lab – React Crash Course 2025**

## **Objective**

* Set up a React environment with Vite
* Learn JSX, functional components, and basic state management
* Build the **starter skeleton** for a simple **Note Keeper** app (completely different from TaskMaster)

---

## **Lab 1.1 – Environment Setup**

**Steps:**

1. Check Node.js & npm versions:

```bash
node -v
npm -v
```

2. Scaffold a new Vite React project:

```bash
npm create vite@latest note-keeper -- --template react
cd note-keeper
npm install
npm run dev
```

3. Open the app in your browser at `http://localhost:5173`.

---

## **Lab 1.2 – Clean Up Default App**

* Open `App.jsx` and remove all default content.
* Add a simple root element:

```jsx
function App() {
  return (
    <div>
      <h1>Note Keeper</h1>
      <p>Welcome to your new React app!</p>
    </div>
  );
}

export default App;
```

* Verify that the browser updates instantly (HMR in action).

---

## **Lab 1.3 – Creating Your First Component**

1. Create a new file: `src/components/Note.jsx`

```jsx
function Note({ title }) {
  return <div className="note">{title}</div>;
}

export default Note;
```

2. Update `App.jsx` to use it:

```jsx
import Note from './components/Note';

function App() {
  return (
    <div>
      <h1>Note Keeper</h1>
      <Note title="First note!" />
      <Note title="Second note!" />
    </div>
  );
}

export default App;
```

* **Goal:** Display multiple notes using a reusable component.

---

## **Lab 1.4 – Adding State with `useState`**

1. Import `useState`:

```jsx
import { useState } from "react";
```

2. Add basic state to track a note input:

```jsx
function App() {
  const [noteInput, setNoteInput] = useState("");
  const [notes, setNotes] = useState([]);

  const addNote = () => {
    if (!noteInput.trim()) return;
    setNotes([...notes, noteInput]);
    setNoteInput("");
  };

  return (
    <div>
      <h1>Note Keeper</h1>
      <input
        type="text"
        value={noteInput}
        onChange={(e) => setNoteInput(e.target.value)}
        placeholder="Enter a new note"
      />
      <button onClick={addNote}>Add Note</button>

      <div>
        {notes.map((note, index) => (
          <Note key={index} title={note} />
        ))}
      </div>
    </div>
  );
}
```

* **Goal:** Type a note, click “Add Note,” and see it appear below.

---

## **Lab 1.5 – Styling (Optional, Quick Visual Feedback)**

* Add some styles to `App.css`:

```css
.note {
  padding: 8px;
  margin: 4px 0;
  border: 1px solid #ccc;
  border-radius: 4px;
  background-color: #fefefe;
}
```

* Verify that notes display with minimal styling.

---

## **Lab 1.6 – Reflection & Notes**

* **Questions for students:**

  1. What happens when you call `setNotes([...notes, noteInput])`?
  2. Why do we need `key` in `.map()`?
  3. How does `useState` trigger re-renders?

* **Learning outcomes:**

  * React environment set up (Node + Vite)
  * Functional components and JSX basics
  * Component reuse
  * Basic state management with `useState`
  * Dynamic rendering of lists

---

✅ **Day 1 Deliverable:**
A working React app that lets users **add notes dynamically**.
*No API, no advanced features yet—just the foundation.*

---
