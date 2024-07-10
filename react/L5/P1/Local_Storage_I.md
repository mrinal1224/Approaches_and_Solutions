# Title : Local Storage I

## Problem Statement

- Write a simple App component that returns an input field of type text. Users can interact with the input field to type in any string they want. You’re meant to store this string in local storage so that every time when the page reloads it pre-fills the input field with the latest known value for the users.

- We have already written some starting code for you.

```jsx
import React from "react";

const App = () => {
  // Edit this component
  /***
   * * Do not edit the data-testid attributes.
   * Use key inputValue to store the data in local storage.
   * */
  return (
    <div>
      <input data-testid="input-id" type="text" />
    </div>
  );
};
export default App;
```

## Demo(take the screenshot and update it to)

<img src="https://www.reacterry.com/_next/image?url=https%3A%2F%2Fimages.prismic.io%2Fcoding-platform%2Ffa94c51c-7b77-48a8-97eb-769d921bd376_localstorage1.gif%3Fauto%3Dcompress%2Cformat&w=3840&q=75">

## Hints

- You can use the setItem and getItem methods available on the global localStorage object to save and read data.
- You can make input a controlled element by saving the current value in the state using useState hook.
- On the first app load, you can initialise the state to the value found in local storage, if no such value is found, then make it an empty string.

## Solution

```jsx
import { useState } from "react";

const App = () => {
  const [value, setValue] = useState(localStorage.getItem("inputValue") || "");

  const handleChange = (e) => {
    setValue(e.target.value);
    localStorage.setItem("inputValue", e.target.value);
  };

  return (
    <div>
      <input
        data-testid="input-id"
        type="text"
        value={value}
        onChange={handleChange}
      />
    </div>
  );
};

export default App;
```

## Solution Approach

In this solution useState creates a state variable value and a function setValue to update the value. The initial value of value the cached inputValue from local storage (if exists) or an empty string.

The handleChange function is called every time the user types into the input field. It updates the value of value by calling setValue and sets the same value in local storage under the key "inputValue".

Finally, the component returns a JSX element that renders an input field with the value of value, and an onChange handler to call handleChange when the user types into the input field.
