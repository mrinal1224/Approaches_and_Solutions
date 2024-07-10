## Title : PureComponent Counter

## **Problem Statement:**

You are tasked with creating a pure component in React that displays a simple counter. The component should increment the counter value by 1 every time the user clicks on a button. However, there's a catch: the component must be pure, meaning it should not mutate its state directly but instead return a new state object whenever a change occurs.

### **Code Stub:**

```jsx
import React, { PureComponent } from "react";

class PureCounter extends PureComponent {
  constructor(props) {
    super(props);
    // Initialize state here
    this.state = {
      counter: 0,
    };
  }

  // Implement the handleClick method to handle button clicks
  handleClick = () => {
    // Update the counter state by 1 without mutating the state directly
    // Hint: Use this.setState method to update the state immutably
    // Your code here
  };

  render() {
    return (
      <div>
        <h2>Pure Counter</h2>
        <p>Count: {this.state.counter}</p>
        {/* Implement the button component to trigger the handleClick method */}
        {/* Your code here */}
      </div>
    );
  }
}

export default PureCounter;
```

### **Instructions:**

1. Implement the `handleClick` method within the `PureCounter` component. This method should be responsible for updating the state `counter` by 1 every time the button is clicked. Ensure that you update the state immutably using `setState`.
2. Add a button component within the render method of `PureCounter` to trigger the `handleClick` method when clicked.
3. Ensure that the component is pure, meaning it should extend `PureComponent` from React. This will help in performance optimization by preventing unnecessary re-renders when the state or props haven't changed.

**Note:**

Ensure to test your implementation by rendering the `PureCounter` component in your application and verifying that the counter increments correctly when the button is clicked.

**Solution Approach:**

To create a pure component in React that displays a counter and increments it on button click, we need to follow these steps:

1. Initialize the state in the constructor with a `counter` variable set to 0.
2. Implement a `handleClick` method to update the `counter` state when the button is clicked. It should use `this.setState` to update the state immutably.
3. Render the current value of the `counter` state in the component's UI.
4. Add a button element that triggers the `handleClick` method when clicked.

To ensure the component is pure and optimally re-renders only when necessary, we'll utilize React's `PureComponent` class.

**Solution Code:**

```jsx
import React, { PureComponent } from "react";

class PureCounter extends PureComponent {
  constructor(props) {
    super(props);
    this.state = {
      counter: 0,
    };
  }

  // Method to handle button click and update counter state
  handleClick = () => {
    // Using the functional form of setState to ensure state update is based on previous state
    this.setState((prevState) => ({
      counter: prevState.counter + 1,
    }));
  };

  render() {
    return (
      <div>
        <h2>Pure Counter</h2>
        <p>Count: {this.state.counter}</p>
        {/* Button triggering handleClick method on click */}
        <button onClick={this.handleClick}>Increment</button>
      </div>
    );
  }
}

export default PureCounter;
```

**Explanation:**

- In the `constructor`, we initialize the component's state with a `counter` variable set to 0.
- The `handleClick` method updates the state immutably by using the functional form of `setState`, which provides the previous state as an argument.
- In the `render` method, we display the current value of the `counter` state and add a button that triggers the `handleClick` method when clicked.
- By extending `PureComponent`, React will perform a shallow comparison of props and state to determine whether the component should re-render, optimizing performance by avoiding unnecessary renders when the state or props haven't changed.
