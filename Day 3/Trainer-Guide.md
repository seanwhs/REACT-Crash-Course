# **React Crash Course 2025 – Day 3 Trainer Guide**

**Theme:** API Integration, Component Patterns & Performance
**Duration:** 6–7 hours

**Prerequisites:**

* Completion of Day 1 & Day 2 labs
* Learners should have a working React project scaffolded and functional
* Familiarity with `useState`, `useEffect`, props, and component extraction

---

## **Session Goals**

By the end of Day 3, learners should be able to:

1. Extract and compose reusable React components (`TaskList`, `TaskItem`)
2. Integrate external APIs and handle side effects
3. Persist state with `localStorage`
4. Apply conditional rendering and dynamic filtering
5. Optimize performance using `useMemo` and `useCallback`
6. Debug React applications effectively

---

## **Lesson Schedule & Trainer Notes**

| Time      | Topic                                     | Trainer Instructions                                                           | Tips / Discussion Prompts                                                     |
| --------- | ----------------------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------- |
| 0:00–0:30 | **Welcome & Recap**                       | Briefly recap Day 2: `useEffect`, component extraction, props, state ownership | Ask: *“Who can explain why `useEffect` is needed for fetching data?”*         |
| 0:30–1:15 | **Advanced Component Patterns**           | Live demo splitting `App.jsx` into `TaskList` & `TaskItem`                     | Emphasize parent owns state, children use props & callbacks                   |
| 1:15–2:15 | **API Integration Lab**                   | Guide learners to fetch API tasks using `useEffect`                            | Check: loading, error, empty states; prompt learners to explain async flow    |
| 2:15–2:30 | **Break**                                 | -                                                                              | -                                                                             |
| 2:30–3:15 | **State Persistence (`localStorage`)**    | Demonstrate saving tasks to `localStorage` and retrieving on load              | Ask: *“What would happen if we didn’t use `localStorage`?”*                   |
| 3:15–4:00 | **Conditional Rendering & Filtering Lab** | Learners implement filter buttons and dynamic UI states                        | Check: UI updates correctly; discuss best practices for conditional rendering |
| 4:00–4:15 | **Break**                                 | -                                                                              | -                                                                             |
| 4:15–5:00 | **Performance Optimization**              | Demo `useMemo` & `useCallback` usage; explain keys in lists                    | Ask: *“How do these hooks prevent unnecessary re-renders?”*                   |
| 5:00–5:45 | **Debugging & Best Practices**            | Show React DevTools usage, console logging of effects                          | Encourage learners to debug any unexpected behavior in their labs             |
| 5:45–6:30 | **Capstone Project Lab**                  | Independent work: integrate all features into TaskMaster Pro                   | Circulate to provide hints, not solutions; check state flow and modularity    |
| 6:30–7:00 | **Wrap-up & Q&A**                         | Review learning objectives, share next steps, answer questions                 | Ask learners to explain one advanced concept they mastered today              |

---

## **Trainer Notes & Tips**

### **1. Teaching Style**

* Use **live coding** for demos; encourage learners to follow along
* Ask **guided questions** to promote critical thinking
* Keep explanations concise; focus on **why** not just **how**

### **2. Common Pitfalls**

* Forgetting dependency arrays in `useEffect` → infinite loops
* Fetching data inside render instead of `useEffect`
* Mutating state directly in child components
* Passing unnecessary props → prop drilling
* Ignoring performance optimizations in lists

### **3. Lab Support**

* Encourage learners to break tasks into small steps
* Only give **hints**, avoid full solutions
* Circulate to check:

  * `App.jsx` manages state
  * Children use props & callbacks only
  * Async fetch, loading, and error handling work correctly
  * UI updates correctly after filtering

### **4. Debugging Guidance**

* Demonstrate React DevTools: inspect state and props flow
* Console.log effects to verify order of execution
* Emphasize immutability to prevent unexpected re-renders

### **5. Capstone Assessment**

* Learners should submit or demonstrate:

  * Modular components (`TaskList`, `TaskItem`)
  * Correct API integration with loading/error handling
  * Persistent state via `localStorage`
  * Filtering & conditional rendering
  * Optimized re-rendering using `useMemo` / `useCallback`

---

## **Discussion Prompts**

* “Why should children never modify parent state directly?”
* “What problems can arise if `useEffect` dependencies are missing?”
* “How does `localStorage` help maintain state across sessions?”
* “Why is memoization important for performance in React apps?”

---

## **Follow-up / Next Steps**

* Explore **state management libraries** for larger apps (Redux, Zustand)
* Add features like task priorities, due dates, or animations
* Practice integrating multiple API endpoints

---

