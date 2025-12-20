# **React Movie Explorer – Starter Template**

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

```jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./App.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

---

## **2. `App.jsx`**

```jsx
import React, { useState, useEffect, useMemo, useCallback } from "react";
import MovieList from "./components/MovieList";
import SearchBar from "./components/SearchBar";
import { fetchMovies } from "./utils/api";

function App() {
  const [movies, setMovies] = useState([]);
  const [search, setSearch] = useState(
    () => localStorage.getItem("search") || ""
  );
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    const getMovies = async () => {
      setLoading(true);
      setError(null);
      try {
        const data = await fetchMovies();
        setMovies(data);
      } catch (err) {
        setError("Failed to fetch movies.");
      } finally {
        setLoading(false);
      }
    };
    getMovies();
  }, []);

  useEffect(() => {
    localStorage.setItem("search", search);
  }, [search]);

  const handleSearchChange = useCallback((value) => {
    setSearch(value);
  }, []);

  const filteredMovies = useMemo(() => {
    return movies.filter((movie) =>
      movie.title.toLowerCase().includes(search.toLowerCase())
    );
  }, [movies, search]);

  return (
    <div className="app-container">
      <h1>React Movie Explorer</h1>
      <SearchBar search={search} onSearchChange={handleSearchChange} />
      {loading && <p>Loading movies...</p>}
      {error && <p>{error}</p>}
      {!loading && !error && (
        <MovieList movies={filteredMovies} />
      )}
      {!loading && !error && filteredMovies.length === 0 && (
        <p>No movies found.</p>
      )}
    </div>
  );
}

export default App;
```

---

## **3. `components/SearchBar.jsx`**

```jsx
import React from "react";

function SearchBar({ search, onSearchChange }) {
  return (
    <input
      type="text"
      placeholder="Search movies..."
      value={search}
      onChange={(e) => onSearchChange(e.target.value)}
    />
  );
}

export default SearchBar;
```

---

## **4. `components/MovieList.jsx`**

```jsx
import React from "react";
import MovieItem from "./MovieItem";

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

---

## **5. `components/MovieItem.jsx`**

```jsx
import React from "react";

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

---

## **6. `utils/api.js`**

```javascript
// Example API helper (using OMDb API or JSON placeholder)
export async function fetchMovies() {
  // Replace with your API endpoint and API key if required
  const API_URL = "https://api.sampleapis.com/movies/action";
  const response = await fetch(API_URL);
  if (!response.ok) throw new Error("Network response was not ok");
  const data = await response.json();

  // Map to consistent structure
  return data.map((item) => ({
    id: item.id || item.title,
    title: item.title,
    poster: item.posterURL || "",
    release_date: item.releaseDate || "N/A",
  }));
}
```

---

## **7. `App.css` (basic styling)**

```css
.app-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
}

.movie-list {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
}

.movie-item {
  width: 150px;
  border: 1px solid #ccc;
  padding: 8px;
  text-align: center;
}

.movie-item img {
  max-width: 100%;
  height: auto;
}
```

---

### ✅ **Features Already Scaffolded**

* API fetch with error/loading handling
* Search input with `useCallback`
* Filtered movie list with `useMemo`
* Components: `MovieList`, `MovieItem`, `SearchBar`
* `localStorage` persistence for search

---

### **Next Steps for Learners**

1. Add **genre or rating filters**
2. Implement **favorites** and persist in `localStorage`
3. Add **movie details modal**
4. Apply **animations or hover effects**
5. Optimize further using `React.memo`

---


Do you want me to do that?
