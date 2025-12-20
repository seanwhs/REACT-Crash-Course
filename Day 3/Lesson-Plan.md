# **React Crash Course 2025 – Day 3 Lesson Plan**

**Theme:** API Integration, Component Patterns & Performance

**Duration:** 6–7 hours (can be split into 3–4 sessions with breaks)

**Prerequisites:**

* Completion of Day 1 & Day 2 labs
* React project scaffolded and functional
* Familiarity with `useState`, `useEffect`, component extraction, and props

---

## **Learning Objectives**

By the end of Day 3, learners will be able to:

1. Extract and compose reusable React components (`TaskList`, `TaskItem`)
2. Integrate external APIs and manage asynchronous side effects
3. Implement loading, error, and empty states
4. Persist application state using `localStorage`
5. Apply filtering and conditional rendering for improved UX
6. Optimize performance with `useMemo` and `useCallback`
7. Debug React applications effectively using DevTools

---

## **Lesson Schedule**

| Time      | Topic                                   | Teaching Method          | Notes / Exercises                                                                                          |
| --------- | --------------------------------------- | ------------------------ | ---------------------------------------------------------------------------------------------------------- |
| 0:00–0:30 | **Welcome & Recap**                     | Lecture                  | Review Day 2 concepts: `useEffect`, component extraction, props & state                                    |
| 0:30–1:15 | **Advanced Component Patterns**         | Lecture + Demo           | Demonstrate splitting TaskMaster app into `TaskList` & `TaskItem`; emphasize state ownership and props     |
| 1:15–2:15 | **API Integration**                     | Guided Lab               | Fetch tasks from API using `useEffect`; handle loading & error states                                      |
| 2:15–2:30 | **Break**                               | -                        | -                                                                                                          |
| 2:30–3:15 | **State Persistence with localStorage** | Lecture + Demo           | Save tasks in `localStorage` and retrieve on app load; explain controlled components                       |
| 3:15–4:00 | **Conditional Rendering & Filtering**   | Guided Lab               | Implement task filtering (All, Active, Completed); show empty & loading states dynamically                 |
| 4:00–4:15 | **Break**                               | -                        | -                                                                                                          |
| 4:15–5:00 | **Performance Optimization**            | Lecture + Demo           | Use `useMemo` for expensive calculations, `useCallback` for callbacks; explain importance of keys in lists |
| 5:00–5:45 | **Debugging & Best Practices**          | Guided Discussion + Demo | Explore React DevTools, console logging for side effects, modular component design                         |
| 5:45–6:30 | **Capstone Project Lab**                | Independent Lab          | Complete TaskMaster Pro – API Edition with all features integrated                                         |
| 6:30–7:00 | **Wrap-up & Q&A**                       | Discussion               | Review learning objectives, discuss additional features, share next steps                                  |

---

## **Teaching Notes**

* **Lecture Style:** Keep concepts short and example-driven; use live coding wherever possible.
* **Guided Labs:** Encourage learners to try code independently; only provide hints, not full solutions.
* **Checkpoints:** After each lab section, ensure learners can:

  * Fetch API data successfully
  * Handle loading, error, and empty states
  * Use `localStorage` to persist tasks
  * Filter tasks dynamically
  * Keep `App.jsx` clean with modular components
* **Assessment:** Observe labs, ask learners to explain reasoning, and verify correct use of hooks and props.

---

## **Materials Needed**

* Day 3 slide deck
* Lab instructions & starter code (from Day 2 app)
* Browser with React DevTools installed
* Code editor (VSCode recommended)
* Access to a free API (e.g., `https://jsonplaceholder.typicode.com/todos?_limit=5`)

---

## **Capstone Project Deliverables**

By the end of Day 3, each learner should have a **production-ready TaskMaster Pro app** with:

1. Reusable `TaskList` & `TaskItem` components
2. API integration with proper `useEffect` usage
3. Loading, error, and empty state handling
4. State persistence with `localStorage`
5. Dynamic filtering (All / Active / Completed)
6. Performance optimizations (`useMemo` / `useCallback`)
7. Clean, modular code

---

## **Follow-up / Next Steps**

* Explore **state management libraries** like Redux or Zustand for larger applications
* Practice more complex API integrations and side-effect patterns
* Extend the TaskMaster app with new features (e.g., due dates, task priorities)

---

