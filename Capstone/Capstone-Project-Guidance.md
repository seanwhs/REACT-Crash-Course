# **React Movie Explorer – Capstone Project Guidance**

**Objective:** Build a **React Movie Explorer** app that fetches, searches, filters, and displays movies with a professional, production-ready structure.

**Learning Goals:**

* Component-driven architecture (`App`, `MovieList`, `MovieItem`, `SearchBar`)
* Side effects & API integration (`useEffect`)
* State management & persistence (`useState`, `localStorage`)
* Conditional rendering & UX feedback (loading, error, empty states)
* Performance optimizations (`useMemo`, `useCallback`)
* Clean, maintainable, reusable code

---

## **Preparation**

**Prerequisites:**

* Completion of Day 1–3 labs
* Node.js + npm installed
* Vite scaffolded React project

**Starter Command:**

```bash
npm create vite@latest movie-explorer -- --template react
cd movie-explorer
npm install
npm run dev
```

---

# **Step 1 – Scaffold Project Structure**

### **Objective**

Set up a clean folder structure for components and utilities.

### **Instructions**

1. Create folders:

   ```
   src/
     ├─ components/
     └─ utils/
   ```
2. Add files:

   * `App.jsx`
   * `main.jsx`
   * `App.css`
   * `components/MovieList.jsx`
   * `components/MovieItem.jsx`
   * `components/SearchBar.jsx`
   * `utils/api.js`

### **Hints**

* Keep components **modular**
* Utilities go into `utils/`

### **Checkpoint**

* Folder structure matches:

```
src/
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

# **Step 2 – Build Root App Component**

### **Objective**

Set up the root component to manage state and render children.

### **Exercise**

1. Import hooks: `useState`, `useEffect`, `useMemo`, `useCallback`.
2. Initialize states:

   * `movies` → `[]`
   * `search` → persisted in `localStorage`
   * `loading` → `true`
   * `error` → `null`
3. Use `useEffect` to fetch movies on mount (call `fetchMovies` from `api.js`)
4. Use another `useEffect` to persist `search` to `localStorage`.
5. Render `<SearchBar />` and `<MovieList />` with conditional rendering for **loading**, **error**, and **empty state**.

### **Hints**

* `filteredMovies` should use `useMemo` for performance
* Pass callbacks via `useCallback` to avoid re-renders

### **Checkpoint**

* App renders loading initially
* API call completes and movies display
* Errors show if API fails

---

# **Step 3 – Create SearchBar Component**

### **Objective**

Allow user to search movies by title.

### **Exercise**

1. Props:

   * `search` → current search term
   * `onSearchChange` → callback function to update search in App
2. Render a controlled input: `value={search}`
3. Trigger `onSearchChange` on `onChange`

### **Hints**

* Keep this **stateless**
* Use `onChange={(e) => onSearchChange(e.target.value)}`

### **Checkpoint**

* Typing in input updates App search state
* Filtered results update dynamically

---

# **Step 4 – Create MovieList & MovieItem Components**

### **Objective**

Render a list of movies with poster, title, and release date.

### **Exercise**

1. `MovieList` props: `movies` → array of movies
2. Map `movies` to `<MovieItem key={movie.id} movie={movie} />`
3. `MovieItem` props: `movie` → object with `title`, `poster`, `release_date`
4. Render a card with:

   * Poster image
   * Title
   * Release date

### **Hints**

* Use proper `key` in `.map()`
* Keep `MovieItem` **stateless and reusable**

### **Checkpoint**

* Movies display as cards
* List updates when `search` changes

---

# **Step 5 – Implement API Integration**

### **Objective**

Fetch movies from an external API and normalize data.

### **Exercise**

1. Create `fetchMovies` function in `utils/api.js`
2. Fetch from a sample API, e.g. `https://api.sampleapis.com/movies/action`
3. Map data to consistent structure:

```js
{
  id: item.id || item.title,
  title: item.title,
  poster: item.posterURL || "",
  release_date: item.releaseDate || "N/A"
}
```

4. Handle errors with `try/catch`

### **Hints**

* Use `async/await` inside `useEffect`
* Update `loading` and `error` states appropriately

### **Checkpoint**

* Movies display from API
* Errors display if fetch fails
* Loading indicator works

---

# **Step 6 – Add Conditional Rendering**

### **Objective**

Improve UX with proper state handling.

### **Exercise**

1. Render **loading** state while fetching
2. Render **error message** if API fails
3. Render **empty state** if no movies match search/filter

### **Hints**

* `filteredMovies.length === 0` → show empty message
* Only show `MovieList` when data exists

### **Checkpoint**

* App handles all four states: loading, error, empty, data

---

# **Step 7 – Implement Filtering & Search**

### **Objective**

Dynamic search and filter functionality.

### **Exercise**

1. Compute `filteredMovies` using `useMemo` based on `search`
2. Update `SearchBar` input to update `search` state in App
3. Test filtering by typing partial movie titles

### **Hints**

* Convert both movie title and search term to lowercase for case-insensitive search

### **Checkpoint**

* Filtering works instantly
* `MovieList` updates correctly

---

# **Step 8 – Persist Search State**

### **Objective**

Persist user search term in `localStorage`.

### **Exercise**

1. On App mount, initialize `search` from `localStorage`
2. Use `useEffect` to update `localStorage` whenever `search` changes

### **Hints**

* Use lazy initialization with `useState(() => localStorage.getItem("search") || "")`

### **Checkpoint**

* Refreshing page keeps the previous search term

---

# **Step 9 – Performance Optimizations**

### **Objective**

Optimize re-renders and computations.

### **Exercise**

1. Wrap `handleSearchChange` in `useCallback`
2. Wrap `filteredMovies` in `useMemo`

### **Hints**

* Helps React avoid recalculating filtered list or re-rendering children unnecessarily

### **Checkpoint**

* App behaves identically
* No unnecessary re-renders in React DevTools

---

# **Step 10 – Styling & UX Improvements**

### **Objective**

Make app visually clean and user-friendly.

### **Exercise**

1. Add CSS to `App.css`:

   * Flexbox layout for movie cards
   * Hover effects
   * Error and loading states styling
2. Optional: add star ratings, genre tags, or modal details

### **Checkpoint**

* App looks presentable and is easy to interact with

---

# **Stretch Challenges**

1. Add **genre or rating filters**
2. Add **favorites feature** saved in `localStorage`
3. Implement **pagination** for long lists
4. Animate card hover or search results
5. Add **sorting by release date**

---

# **End-of-Project Checklist**

| Feature                   | Status |
| ------------------------- | ------ |
| Fetch movies from API     | ✅      |
| Loading indicator         | ✅      |
| Error handling            | ✅      |
| Search & filter           | ✅      |
| Persist search state      | ✅      |
| Reusable components       | ✅      |
| Performance optimizations | ✅      |
| Conditional rendering     | ✅      |
| Basic CSS styling         | ✅      |
| Optional stretch features | ☐      |

---

# **Instructor Notes / Guidance**

* **Do not provide full solutions immediately**
* Encourage learners to **plan components before coding**
* Prompt learners to **explain why `useEffect` and dependency arrays are needed**
* Encourage **clean separation of concerns**
* Use **React DevTools** to debug re-renders

---

This workbook **guides learners step by step**, provides **hints and checkpoints for each feature**, and aligns with the **course learning objectives**.

---

