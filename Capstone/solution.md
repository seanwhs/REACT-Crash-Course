# **Complete Solution – React Movie Explorer**

**Objective:** Demonstrate a production-ready React application using best practices:

* Component architecture
* API integration with `useEffect`
* State management (`useState`)
* Performance optimizations (`useMemo`, `useCallback`)
* Persistence via `localStorage`
* Conditional rendering for loading/error/empty states

---

## **Project Structure**

```
movie-explorer/
 ├─ package.json
 ├─ vite.config.js
 ├─ index.html
 └─ src/
     ├─ main.jsx
     ├─ App.jsx
     ├─ App.css
     ├─ components/
     │   ├─ MovieList.jsx
     │   ├─ MovieItem.jsx
     │   └─ SearchBar.jsx
     └─ utils/
         └─ api.js
```

---

## **1. `main.jsx`**

Entry point that renders the root component.

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./App.css";

// ReactDOM.createRoot initializes React in the DOM
ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

**Explanation:**

* `React.StrictMode` helps detect unsafe lifecycles, legacy API usage, and potential side effects.
* `main.jsx` should remain minimal – its only job is to render `<App />`.

---

## **2. `App.jsx`**

Root component managing **state, API calls, filtering, and persistence**.

```jsx
import React, { useState, useEffect, useMemo, useCallback } from "react";
import MovieList from "./components/MovieList";
import SearchBar from "./components/SearchBar";
import { fetchMovies } from "./utils/api";

function App() {
  // State: stores list of movies fetched from API
  const [movies, setMovies] = useState([]);

  // State: search query, persisted in localStorage
  const [search, setSearch] = useState(
    () => localStorage.getItem("search") || ""
  );

  // Loading & error states for UX
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  /**
   * Fetch movies from API on component mount
   * useEffect with empty dependency array ensures this runs once
   */
  useEffect(() => {
    const getMovies = async () => {
      setLoading(true); // start loading
      setError(null);   // reset error
      try {
        const data = await fetchMovies();
        setMovies(data);
      } catch (err) {
        setError("Failed to fetch movies."); // handle API errors
      } finally {
        setLoading(false); // stop loading
      }
    };
    getMovies();
  }, []);

  /**
   * Persist search query in localStorage
   * Ensures page reload keeps the last search term
   */
  useEffect(() => {
    localStorage.setItem("search", search);
  }, [search]);

  /**
   * Callback passed to SearchBar
   * useCallback prevents unnecessary re-renders of children
   */
  const handleSearchChange = useCallback((value) => {
    setSearch(value);
  }, []);

  /**
   * Filter movies based on search query
   * useMemo prevents recalculating unless movies or search change
   */
  const filteredMovies = useMemo(() => {
    return movies.filter((movie) =>
      movie.title.toLowerCase().includes(search.toLowerCase())
    );
  }, [movies, search]);

  return (
    <div className="app-container">
      <h1>React Movie Explorer</h1>

      {/* Search input */}
      <SearchBar search={search} onSearchChange={handleSearchChange} />

      {/* Conditional rendering */}
      {loading && <p>Loading movies...</p>}
      {error && <p className="error">{error}</p>}
      {!loading && !error && filteredMovies.length === 0 && (
        <p>No movies found.</p>
      )}

      {/* Display movie list */}
      {!loading && !error && filteredMovies.length > 0 && (
        <MovieList movies={filteredMovies} />
      )}
    </div>
  );
}

export default App;
```

**Key Explanations:**

* **State Management:** `useState` manages movies, search query, loading, and error states.
* **Side Effects:** `useEffect` fetches data once when the component mounts.
* **Persistence:** Search term saved to `localStorage` with a `useEffect` watcher.
* **Performance:** `useMemo` avoids re-filtering the movies array unnecessarily; `useCallback` ensures stable function references for child components.
* **Conditional Rendering:** Handles **loading**, **error**, **empty**, and **data available** states.

---

## **3. `components/SearchBar.jsx`**

Reusable search input component.

```jsx
import React from "react";

/**
 * Props:
 *  - search: current search query
 *  - onSearchChange: callback to update search query in parent
 */
function SearchBar({ search, onSearchChange }) {
  return (
    <input
      type="text"
      placeholder="Search movies..."
      value={search}
      onChange={(e) => onSearchChange(e.target.value)}
      className="search-bar"
    />
  );
}

export default SearchBar;
```

**Explanation:**

* Stateless component
* Controlled input – `value` comes from parent
* Calls `onSearchChange` callback when input changes

---

## **4. `components/MovieList.jsx`**

Renders a list of `MovieItem` components.

```jsx
import React from "react";
import MovieItem from "./MovieItem";

/**
 * Props:
 *  - movies: array of movie objects
 */
function MovieList({ movies }) {
  return (
    <div className="movie-list">
      {movies.map((movie) => (
        <MovieItem key={movie.id} movie={movie} />
      ))}
    </div>
  );
}

export default MovieList;
```

**Explanation:**

* Loops through movies array and renders `MovieItem`
* `key` prop ensures proper list reconciliation by React

---

## **5. `components/MovieItem.jsx`**

Displays a single movie.

```jsx
import React from "react";

/**
 * Props:
 *  - movie: object with title, poster, release_date
 */
function MovieItem({ movie }) {
  return (
    <div className="movie-item">
      {movie.poster && <img src={movie.poster} alt={movie.title} />}
      <h3>{movie.title}</h3>
      <p>Release: {movie.release_date}</p>
    </div>
  );
}

export default MovieItem;
```

**Explanation:**

* Stateless, reusable component
* Displays poster, title, release date
* Can easily be extended with additional info (rating, genre)

---

## **6. `utils/api.js`**

API helper to fetch movie data.

```javascript
/**
 * Fetch movies from public API
 * Returns array of movie objects with id, title, poster, release_date
 */
export async function fetchMovies() {
  // Example: Sample Movies API
  const API_URL = "https://api.sampleapis.com/movies/action";

  const response = await fetch(API_URL);
  if (!response.ok) throw new Error("Network response was not ok");

  const data = await response.json();

  // Map to consistent structure for app
  return data.map((item) => ({
    id: item.id || item.title,
    title: item.title,
    poster: item.posterURL || "",
    release_date: item.releaseDate || "N/A",
  }));
}
```

**Explanation:**

* Handles API call and error checking
* Normalizes data into a consistent structure for the app

---

## **7. `App.css`**

Basic styling for the application.

```css
.app-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
  text-align: center;
}

.search-bar {
  width: 100%;
  max-width: 400px;
  padding: 8px;
  margin-bottom: 20px;
  font-size: 16px;
}

.movie-list {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  justify-content: center;
}

.movie-item {
  width: 150px;
  border: 1px solid #ccc;
  padding: 8px;
  border-radius: 4px;
  transition: transform 0.2s;
}

.movie-item:hover {
  transform: scale(1.05);
}

.movie-item img {
  width: 100%;
  height: auto;
}

.error {
  color: red;
}
```

**Explanation:**

* Responsive layout using flexbox
* Hover animation for interactivity
* Error messages styled in red
* Search bar and movie cards styled for readability

---

## **8. Optional Enhancements / Stretch Features**

* **Genre filter:** Add select input to filter by genre
* **Favorites:** Add heart icon to mark favorite movies (persist in `localStorage`)
* **Sorting:** Sort by release date or rating
* **Pagination:** Show movies in pages
* **Details modal:** Show movie synopsis and actors on click

---

## **9. How it Works – Step by Step**

1. **App mounts** → `useEffect` triggers `fetchMovies()`
2. API data is stored in `movies` state
3. `SearchBar` receives `search` and `onSearchChange` props
4. User types in search → `handleSearchChange` updates `search` state
5. `filteredMovies` is computed via `useMemo`
6. `MovieList` renders all `MovieItem` components
7. Conditional rendering shows **loading**, **error**, or **empty state** as needed
8. Search term is persisted in `localStorage` for page reloads

---

## ✅ **Learning Outcomes Demonstrated**

* **React fundamentals:** Components, props, state
* **Hooks:** `useState`, `useEffect`, `useMemo`, `useCallback`
* **Side effects & API integration**
* **Conditional rendering**
* **Performance optimization**
* **Component architecture & reusability**
* **State persistence**


