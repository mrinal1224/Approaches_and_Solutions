## Title : Product Filter

### Problem

**Problem Statement** Build a dynamic product filter application using React. This application will allow users to filter a list of products by category without any server or API calls, demonstrating handling of state and rendering based on user input.

**Requirements:**

1. Display a list of products. Each product has a name, price, and category.
2. Provide a set of checkboxes that allow users to select which categories to view.
3. The product list should update in real-time as users check/uncheck categories.
4. No use of external APIs; all data should be handled within the app's state.

### Initial Code Setup

This React code stub provides the basic structure of the application, including imports, a main component, and placeholders for key parts of the functionality.

```javascript
import React, { useState } from "react";

const ProductFilterApp = () => {
  const [selectedCategories, setSelectedCategories] = useState([]);

  // Example product data
  const products = [
    { id: 1, name: "Apple", category: "Fruits", price: "$1" },
    { id: 2, name: "Carrot", category: "Vegetables", price: "$0.50" },
    { id: 3, name: "Chicken", category: "Meat", price: "$5" },
    { id: 4, name: "Fish", category: "Meat", price: "$3" },
    { id: 5, name: "Banana", category: "Fruits", price: "$2" },
  ];

  const categories = ["Fruits", "Vegetables", "Meat"];

  const handleCategoryChange = (category) => {
    // Implement category selection logic
  };

  const filterProducts = () => {
    // Implement product filtering logic
  };

  return (
    <div>
      <h1>Product Filter</h1>
      {/* Category checkboxes */}
      <div>
        {categories.map((category) => (
          <div key={category}>
            <input
              type="checkbox"
              value={category}
              onChange={() => handleCategoryChange(category)}
            />{" "}
            {category}
          </div>
        ))}
      </div>
      {/* Product list */}
      <ul>
        {filterProducts().map((product) => (
          <li key={product.id}>
            {product.name} - {product.price}
          </li>
        ))}
      </ul>
    </div>
  );
};

export default ProductFilterApp;
```

### Final Solution

Here is how you might implement the missing parts:

```javascript
const handleCategoryChange = (category) => {
  if (selectedCategories.includes(category)) {
    setSelectedCategories(selectedCategories.filter((cat) => cat !== category));
  } else {
    setSelectedCategories([...selectedCategories, category]);
  }
};

const filterProducts = () => {
  return selectedCategories.length === 0
    ? products
    : products.filter((product) =>
        selectedCategories.includes(product.category)
      );
};
```

### Hints and Solution Approach

1. **Manage State:** Use the `useState` hook to manage which categories are selected.
2. **Handle Changes:** Implement `handleCategoryChange` to add or remove categories from the `selectedCategories` state based on user interaction.
3. **Filter Products:** In `filterProducts`, return products that match any of the categories in `selectedCategories`.
4. **Conditional Rendering:** Conditionally render products based on the filtered results.
