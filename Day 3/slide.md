React Crash Course 2025 – Day 3
Slide 1 – Day 3 Overview

Topics:

Advanced Components & Props

API Integration with useEffect

State Persistence (localStorage)

Conditional Rendering & Filters

Best Practices & Optimization

Slide 2 – Advanced Component Patterns

Extract reusable components: TaskItem, TaskList

Pass props and callbacks for controlled updates

Compose components for modularity and readability

Slide 3 – API Integration

Use useEffect to fetch data from APIs

Handle async operations and errors

Manage loading states

useEffect(() => {
  fetch("https://jsonplaceholder.typicode.com/todos")
    .then(res => res.json())
    .then(data => setTasks(data));
}, []);

Slide 4 – State Persistence

Persist tasks with localStorage

useEffect(() => localStorage.setItem("tasks", JSON.stringify(tasks)), [tasks]);


Load state on mount

useEffect(() => setTasks(JSON.parse(localStorage.getItem("tasks")) || []), []);

Slide 5 – Conditional Rendering & Filters

Show empty state if no tasks

Filter tasks: All / Active / Completed

Highlight completed tasks

tasks.filter(t => t.completed)

Slide 6 – Best Practices

Immutability → use new arrays/objects

Keys in lists → stable DOM nodes

Performance → useMemo, useCallback

Debugging → React DevTools, console.log

Slide 7 – Day 3 Takeaways

Modular, maintainable React apps

API integration and side-effect management

Persisted state with localStorage

Conditional rendering and dynamic filters

Advanced patterns for performance and maintainability
