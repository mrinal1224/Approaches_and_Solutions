# Topic : Local Storage II - hook

## Problem Statement

You need to create a custom hook called useLocalStorage(key, initialValue) that can be used to store and retrieve data from local storage. You should use the key prop as the key for the data in local storage and initialValue as the initial value.

The hook should return an object with two properties:

- the current value of the data, which should be initialized to the value stored in local storage (if it exists), or the initialValue argument (if it doesn't)
- a function that can be used to update the value of the data in local storage

Every time the value of the data is updated, the hook should update the corresponding value in local storage.

Please see the example below for the required return object.

We have already written some starting code for you.

## Demo

<img src ="https://www.reacterry.com/_next/image?url=https%3A%2F%2Fimages.prismic.io%2Fcoding-platform%2Ffa94c51c-7b77-48a8-97eb-769d921bd376_localstorage1.gif%3Fauto%3Dcompress%2Cformat&w=3840&q=75">

## hints

- Use the useState hook to create a state variable for the value of the data to be stored in local storage. Initialise the state variable using the useState hook's initialiser function.

- Use the useEffect hook to write the data to local storage whenever it changes. Make sure to pass the value and the key to useEffect's dependencies array to ensure that it only updates when the value changes.

## solution

```jsx
//App.jsx
import { useState, useEffect } from "react";

export const useLocalStorage = (key, initialValue) => {
  const [value, setValue] = useState(() => {
    const storedValue = localStorage.getItem(key);
    return storedValue !== null ? storedValue : initialValue;
  });

  useEffect(() => {
    localStorage.setItem(key, value);
  }, [value, key]);

  return { value, setValue };
};

const App = () => {
  const { value, setValue } = useLocalStorage("inputValue", "");

  const handleChange = (e) => {
    setValue(e.target.value);
  };

  return (
    <div>
      <input type="text" value={value} onChange={handleChange} />
    </div>
  );
};

export default App;
```

## Solution Approach

To implement the `useLocalStorage` hook:

1. **Initialize State**: Use `useState` to create a state variable `value`. Initialize it with the value retrieved from local storage using the provided `key`. Default to `initialValue` if no data is found.

2. **Update Local Storage**: Utilize `useEffect` to watch for changes to `value`. Update the corresponding value in local storage whenever `value` changes.

3. **Return Accessors**: Return an object with `value` and `setValue` functions, allowing components to access and modify the stored data easily.
