**Raw Problem**

**Implement a Throttle Function in JavaScript**

In this coding challenge, you will practice implementing a throttle function in JavaScript. After you've learnt about throttling, this exercise will give you hands-on experience in creating a functional throttle utility.

**Instructions:**

1.  You are provided with a partially completed function named throttle. Your task is to complete the implementation to create a functional throttle utility.
2.  The throttle function should take two arguments: fn (the function to be throttled) and time (the time interval in milliseconds).
3.  Test your throttle function with different time intervals and functions.

**Important Pointers:**

- Throttling is useful in scenarios where you want to limit the frequency of a function's execution to a specified time interval.
- Be sure to capture the function's context (this) and arguments inside the inner function.
- Experiment with different functions and time intervals to see how the throttle function behaves.

**Function Signature and Test Case:**

```js
function throttle(fn, time) {}

// Test Cases

const throttledFunc = throttle((value) => console.log(value), 200);

throttledFunc("First call"); // Should log
throttledFunc("Second call"); // Should not log
```

**Hints:**
Here are six short one-line hints corresponding to the solution:

1. Initialize a variable to store the timer ID for throttling.
2. If the timer ID exists, exit the function to prevent execution.
3. Create a timer using `setTimeout` when the function is allowed to execute.
4. Use `fn.call(context, ...args)` to invoke the original function with context and arguments.
5. Reset the timer variable to `null` after the function execution.
6. Test your `throttle` function with various time intervals and functions.

**Solution Approach**

1. The `throttle` function accepts two parameters: `fn` (the function to be throttled) and `time` (the time interval in milliseconds).

2. Inside the `throttle` function, a variable named `timeout` is declared and initialized with `null`. This variable will store the timer ID used for throttling.

3. The `return` statement defines an inner function that will be returned by the `throttle` function. This inner function is the throttled version of the original function that will be called when the throttled action occurs.

4. Inside the inner function:

   - If the `timeout` value is truthy (indicating that a timer is already set), the function immediately exits without further execution. This prevents the function from being executed too frequently.
   - If the `timeout` value is falsy (indicating that no timer is set), the current `this` context and `arguments` are captured. This ensures that the context and arguments of the original function are preserved.
   - A callback function named `later` is defined. This callback will be executed after the specified `time` interval.
   - Inside the `later` callback:
     - The original function (`fn`) is called using `fn.call(context, ...args)`, ensuring that the function is invoked with the correct context and arguments.
     - The `timeout` variable is reset to `null` after the function execution. This allows the function to be throttled again after the time interval has passed.

5. By using the `throttle` function, you can now control the frequency of execution of the provided function, ensuring that it is called at a controlled rate.

**Solution**

```javascript
// Complete the function below
function throttle(fn, time) {
  let timeout; // Initialize the timer variable

  // Return the throttled function
  return function () {
    // If the timer is already set, exit the function
    if (timeout) return;

    const context = this; // Capture the context
    const args = arguments; // Capture the arguments

    // Define a callback function for the timer
    const later = () => {
      // Call the original function with context and arguments
      fn.call(context, ...args);

      // Reset the timer variable after execution
      timeout = null;
    };

    // Set the timer using setTimeout
    timeout = setTimeout(later, time);
  };
}
```
