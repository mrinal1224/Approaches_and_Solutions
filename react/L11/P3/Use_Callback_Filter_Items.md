## Title : Use Callback Filter Items

### Problem Statement

In a React application, a component displays a list of items. There is a button that, when clicked, filters the list based on a specific condition. However, the filter function is defined within the component and gets recreated every time the component re-renders. This behavior is inefficient, especially as this function is passed down to child components, causing them to unnecessarily re-render due to the perceived change in props.

### Code Stub (Before Optimization)

```jsx
import React, { useState } from "react";

function ItemList() {
  const [items, setItems] = useState([
    "Apple",
    "Banana",
    "Cherry",
    "Date",
    "Elderberry",
  ]);
  const [query, setQuery] = useState("");

  const filterItems = () => {
    return items.filter((item) =>
      item.toLowerCase().includes(query.toLowerCase())
    );
  };

  return (
    <div>
      <input
        type="text"
        value={query}
        onChange={(e) => setQuery(e.target.value)}
      />
      <ul>
        {filterItems().map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </div>
  );
}

export default ItemList;
```

### Problem and Optimization Task

Your task is to optimize the `ItemList` component by using the `useCallback` hook to prevent the unnecessary re-creation of the `filterItems` function every time the component re-renders. This optimization is crucial for maintaining performance, particularly if `filterItems` is passed as a prop to child components.

### Hints

1. Review how `useCallback` can be used to memoize functions.
2. Identify the dependencies that dictate when `useCallback` should recompute the function.
3. Use `useCallback` to ensure that the `filterItems` function is only recreated when its dependencies change.

### Optimized Solution

```jsx
import React, { useState, useCallback } from "react";

function ItemList() {
  const [items, setItems] = useState([
    "Apple",
    "Banana",
    "Cherry",
    "Date",
    "Elderberry",
  ]);
  const [query, setQuery] = useState("");

  const filterItems = useCallback(() => {
    console.log("Filtering items...");
    return items.filter((item) =>
      item.toLowerCase().includes(query.toLowerCase())
    );
  }, [items, query]); // Dependencies

  return (
    <div>
      <input
        type="text"
        value={query}
        onChange={(e) => setQuery(e.target.value)}
      />
      <ul>
        {filterItems().map((item, index) => (
          <li key={index}>{item}</li>
        ))}
      </ul>
    </div>
  );
}

export default ItemList;
```

### Solution Approach

1. Import the `useCallback` hook from React.
2. Wrap the `filterItems` function declaration with `useCallback`.
3. Set the dependencies of `useCallback` to include both `items` and `query`, as these influence when the function should be updated.
