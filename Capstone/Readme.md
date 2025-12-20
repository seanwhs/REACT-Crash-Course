# **Capstone Project – Movie Explorer**

**Objective:** Build a **React Movie Explorer** app that allows users to browse, search, and filter movies fetched from an external API. The project demonstrates **component architecture, hooks, API integration, state management, filtering, and performance optimizations**.

**Estimated Time:** 6–8 hours

**Prerequisites:** Completion of Day 1–3 labs, working React project scaffolded with Vite

---

## **Project Overview**

Movie Explorer is an application where users can:

* View a list of movies fetched from a public API
* Search movies by title
* Filter movies by genre or rating
* View movie details (title, release date, poster)
* Handle loading, error, and empty states
* Persist search filters in `localStorage`
* Use reusable, modular components (`MovieList`, `MovieItem`, `SearchBar`)
* Optimize performance with `useMemo` and `useCallback`

---

## **Project Structure**

```
src/
 ├─ main.jsx               # Entry point
 ├─ App.jsx                # Root component
 ├─ components/
 │   ├─ MovieList.jsx
 │   ├─ MovieItem.jsx
 │   └─ SearchBar.jsx
 ├─ App.css                # Styles
 └─ utils/
     └─ api.js             # API helper functions
```

---

## **Functional Requirements**

### **1. Fetch Movies**

* Fetch movies from [The Movie Database API](https://developers.themoviedb.org/) or [OMDb API](http://www.omdbapi.com/)
* Use `useEffect` for API calls
* Handle loading and error states

### **2. Search & Filter**

* **SearchBar component** to search by movie title
* **Filters** for genre or rating
* Filtered results should update dynamically using `useMemo`

### **3. Component Patterns**

* `MovieList` renders a list of `MovieItem`s
* `MovieItem` displays movie poster, title, and release date
* `SearchBar` manages search input and filter options
* `App.jsx` manages state and passes props/callbacks

### **4. State Persistence**

* Persist search input and selected filters in `localStorage`
* Load persisted state on app start

### **5. Conditional Rendering**

* Show **Loading** while fetching
* Show **Error** message if fetch fails
* Show **Empty State** if no movies match search/filter

### **6. Performance Optimization**

* Memoize filtered movie list with `useMemo`
* Memoize event handlers passed to children with `useCallback`
* Use proper **keys** for list items

---

## **Stretch Challenges**

* Add **pagination** for large movie lists
* Include a **favorites feature** (persisted in `localStorage`)
* Display **movie ratings visually** (stars or bars)
* Animate movie card hover or search results
* Sort movies by release date or rating

---

## **Deliverables**

Learners should submit or demonstrate:

* Fully working **React Movie Explorer** app
* Modular, reusable components (`MovieList`, `MovieItem`, `SearchBar`)
* API integration with proper loading/error handling
* Search and filter functionality
* State persistence with `localStorage`
* Optimized performance using `useMemo` / `useCallback`
* Clean, maintainable, and readable code

---

## **Assessment Criteria**

| Area          | Expected Outcome                                |
| ------------- | ----------------------------------------------- |
| Functionality | Search, filter, and display movies correctly    |
| API Fetch     | Async fetching works, handles loading & errors  |
| Components    | Reusable, modular, props-driven components      |
| Props & State | One-way data flow, state managed in App         |
| Persistence   | Search/filter state persists via `localStorage` |
| Performance   | Memoization used effectively, keys present      |
| UX            | Loading, error, empty states handled well       |
| Code Quality  | Clean, maintainable, and readable code          |

---


