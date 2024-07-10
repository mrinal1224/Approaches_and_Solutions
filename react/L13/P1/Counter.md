## Title : Counter

**Problem Statement:**

You are tasked with creating a simple counter component using React. The counter should be implemented as a class-based component and should have the following functionalities:

1. Display an initial count of 0.
2. Render two buttons: one for incrementing the count and one for decrementing the count.
3. Update the count accordingly when the buttons are clicked.

You are provided with a basic structure for the Counter component. Your task is to complete the component so that it functions as described above.

**Code Stub:**

```javascript
import React, { Component } from 'react';

class Counter extends Component {
  constructor(props) {
    super(props);
    // Initialize state here
  }

  // Implement methods here

  render() {
    return (
      <div>
        <h2>Counter</h2>
        <div>
          {/* Display count here */}
        </div>
        <button onClick={/* Implement onClick for increment */}>Increment</button>
        <button onClick={/* Implement onClick for decrement */}>Decrement</button>
      </div>
    );
  }
}

export default Counter;
```

**Instructions:**

1. **Initialize the State:**
   In the constructor of the Counter component, initialize the state with a `count` property set to 0. Remember, state initialization is crucial for tracking changes in your component.

2. **Implement the `onClick` Event Handlers:**
   - For incrementing the count: Implement an `incrementCount` method. This method should update the state, increasing the `count` by 1.
   - For decrementing the count: Implement a `decrementCount` method. This method should update the state, decreasing the `count` by 1.

**Hints:**

- To modify the state in a class-based component, use `this.setState()`. This ensures the component re-renders and displays the updated state.
- Bind the `incrementCount` and `decrementCount` methods in the constructor or use arrow functions to ensure they have access to `this`.

3. **Bind and Attach the Event Handlers:**
   In your render method, bind the `incrementCount` and `decrementCount` methods to the respective buttons. This will make sure that the count updates correctly when the buttons are clicked.

4. **Update the UI:**
   Display the current count in the render method's div element, ensuring it updates when either button is clicked.

**Solution Approach:**

To solve this problem, we need to complete the Counter component by implementing its state management and event handlers. Here's the approach we'll take:

1. **Initialize the state in the constructor:** We'll initialize the state with a property `count` set to 0.

2. **Implement event handlers:**

   - **Increment:** We'll implement an `incrementCount` method that updates the count by incrementing it by 1.
   - **Decrement:** We'll implement a `decrementCount` method that updates the count by decrementing it by 1.

3. **Bind event handlers:** We'll bind the event handlers to the respective buttons in the render method.

4. **Update the UI:** We'll ensure that the UI displays the current count and updates accordingly when the buttons are clicked.

**Solution Code:**

```javascript
import React, { Component } from "react";

class Counter extends Component {
  constructor(props) {
    super(props);
    this.state = {
      count: 0,
    };
  }

  incrementCount = () => {
    this.setState((prevState) => ({
      count: prevState.count + 1,
    }));
  };

  decrementCount = () => {
    this.setState((prevState) => ({
      count: prevState.count - 1,
    }));
  };

  render() {
    return (
      <div>
        <h2>Counter</h2>
        <div>Count: {this.state.count}</div>
        <button onClick={this.incrementCount}>Increment</button>
        <button onClick={this.decrementCount}>Decrement</button>
      </div>
    );
  }
}

export default Counter;
```

**Explanation:**

- We initialize the state inside the constructor with `count` set to 0.
- `incrementCount` and `decrementCount` methods are defined to update the count by incrementing and decrementing respectively using `setState`.
- Event handlers `incrementCount` and `decrementCount` are bound to the respective buttons in the render method.
- The UI displays the current count from the state, and it updates accordingly when the buttons are clicked.
