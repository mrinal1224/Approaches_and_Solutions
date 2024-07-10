## Title : Implement Debouncing

### Problem Statement: Implement Debouncing in React with Static Data

For this task, you are required to optimize an existing React component that includes a search input field for filtering a list of items. The original component filters the list immediately as the user types, leading to potentially inefficient rendering. You will modify the component by implementing debouncing to reduce unnecessary renders when the user types.

#### Current Code Stub:

```jsx
import React, { useState, useEffect } from "react";

const dataList = [
  { id: 1, name: "Apple" },
  { id: 2, name: "Banana" },
  { id: 3, name: "Cherry" },
  { id: 4, name: "Date" },
  { id: 5, name: "Elderberry" },
];

function SearchComponent() {
  const [query, setQuery] = useState("");
  const [filteredData, setFilteredData] = useState(dataList);

  useEffect(() => {
    const results = dataList.filter((item) =>
      item.name.toLowerCase().includes(query.toLowerCase())
    );
    setFilteredData(results);
  }, [query]);

  return (
    <div>
      <input
        type="text"
        value={query}
        onChange={(e) => setQuery(e.target.value)}
      />
      <ul>
        {filteredData.map((item) => (
          <li key={item.id}>{item.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default SearchComponent;
```

#### Requirements:

1. Implement debouncing in the `SearchComponent` to delay the filtering process until the user has stopped typing for a specified duration of 300 milliseconds.
2. Ensure that the debouncing logic effectively handles rapid typing by the user, reducing the number of renderings.

#### Hints:

1. **Hint 1**: Utilize `setTimeout` and `clearTimeout` to manage the delay.
2. **Hint 2**: Use `useRef` to hold a reference to the timeout so it can be cleared when necessary without triggering re-renders.
3. **Hint 3**: Adjust the `useEffect` cleanup function to manage the timeout, ensuring it's cleared when the component unmounts or the query changes.

#### Debounced Code Solution:

```jsx
import React, { useState, useEffect, useRef } from "react";

const dataList = [
  { id: 1, name: "Apple" },
  { id: 2, name: "Banana" },
  { id: 3, name: "Cherry" },
  { id: 4, name: "Date" },
  { id: 5, name: "Elderberry" },
];

function SearchComponent() {
  const [query, setQuery] = useState("");
  const [filteredData, setFilteredData] = useState(dataList);
  const timeoutId = useRef(null);

  useEffect(() => {
    if (timeoutId.current) {
      clearTimeout(timeoutId.current);
    }
    timeoutId.current = setTimeout(() => {
      const results = dataList.filter((item) =>
        item.name.toLowerCase().includes(query.toLowerCase())
      );
      setFilteredData(results);
    }, 300);

    return () => {
      clearTimeout(timeoutId.current);
    };
  }, [query]);

  return (
    <div>
      <input
        type="text"
        value={query}
        onChange={(e) => setQuery(e.target.value)}
      />
      <ul>
        {filteredData.map((item) => (
          <li key={item.id}>{item.name}</li>
        ))}
      </ul>
    </div>
  );
}

export default SearchComponent;
```

### Solution Approach:

1. Import `useRef` from React to create a reference for the timeout, allowing it to persist without causing extra renders.
2. Implement the `setTimeout` inside the `useEffect`, ensuring you clear any previous timeout every time the `query` changes or the component is about to unmount. This prevents outdated filter operations from completing if the input has changed.
3. Set a debounce duration of 300 milliseconds.
