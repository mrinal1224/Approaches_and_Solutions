# Title: Fetch Data

## Description:

Your task is to create a React component that fetches and displays user information from an API. Specifically, the component should make a GET request to "https://jsonplaceholder.typicode.com/users/1" and display the fetched user's name, email, and username. The component should initially display a loading placeholder text until the data is fetched successfully.

#### Functional Requirements

1. **Data Fetching**:
   - Implement an asynchronous operation within the component to fetch user data from the provided URL upon component mounting.
2. **State Management**:
   - Utilize React's `useState` hook to manage the fetched data state within your component.
3. **Effect Hook**:

   - Use React's `useEffect` hook to trigger the data fetching operation when the component mounts. Ensure that the fetching operation is performed only once.

4. **Conditional Rendering**:

   - Display a placeholder text (`<h2>Loading data...</h2>`) while the data is being fetched.
   - Once the data is fetched, display the user's name, email, and username.
   - If there is an error, show the error like (`<h2>Error fetching data</h2>`)

## solution

```jsx
import React, { useState, useEffect } from "react";

function GetData() {
  const [data, setData] = useState(null);
  //    http -> call -> update the state -> rerender
  function fn() {
    async function fetchData() {
      console.log("useEffect ran");
      const response = await fetch(
        "https://jsonplaceholder.typicode.com/users/1"
      );
      const user = await response.json();
      console.log(data);
      setData(user);
    }
    fetchData();
  }
  // hook -> given react
  useEffect(fn, []);
  console.log("Render");

  return (
    <>
      {data == null ? (
        <h2>Placeholder loading the data....</h2>
      ) : (
        <>
          <h2>Name : {data.name}</h2>
          <h2>Email : {data.email}</h2>
          <h2>username : {data.username}</h2>
        </>
      )}
    </>
  );
}

export default GetData;
```

## Solution Approach

1. **Setting Up State**: Use the `useState` hook to create a state variable to store the fetched data. Initialize this state as `null` or with an initial state indicating that data has not yet been loaded.

2. **Fetching Data**: Inside the `useEffect` hook, define an asynchronous function to fetch data from the given API endpoint. Use the `fetch` API followed by `.json()` to parse the response as JSON. Once the data is fetched, update your component's state with this data.

3. **Handling Loading State**: Before the data is fetched, display a placeholder or loading message. This can be done by checking if the state variable for your data is still `null` or contains the fetched data.

4. **Displaying Data**: Once the data is fetched and stored in your component's state, use conditional rendering to display the data instead of the loading message. Extract the desired fields from your state variable and render them in the component.

5. **Error Handling**: Optionally, include error handling logic to display a message if the data fetching fails.
