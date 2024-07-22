**Raw Problem**

**Implement a Debounce Function in JavaScript**

In this problem, you will solidify your understanding of debouncing by creating your own debounce function in JavaScript. After learning about debouncing, this hands-on challenge will help you apply the concept and develop a functional debounce utility.

**Instructions:**

1.  You are provided with a partially completed function named debounce. Your task is to complete the implementation to create a working debounce utility.
2.  The debounce function should take two arguments: func (the function to be debounced) and wait (the time interval in milliseconds).
3.  Test your debounce function with various scenarios, including different debounce intervals and functions.

**Important pointers:**

- Remember that debouncing is useful in scenarios where you want to delay the execution of a function until a certain amount of time has passed without additional calls.
- To test your implementation, create a test function that logs a message to the console. Use your debounce function to debounce the test function and observe the behavior.

**Function Signature and Test Case:**

```js
function debounce(func, wait) {}

// Test Cases

const debouncedFunc = debounce((value) => console.log(value), 200);

debouncedFunc("First call"); // Should not log immediately
debouncedFunc("Second call"); // Should cancel the previous and set a new timeout
// Wait for 200 ms
// Should log "Second call" after 200 ms
```

**Hints:**

- Use a variable to store the timer ID for debouncing.
- Clear any existing timer using window.clearTimeout(timer) before setting a new one.
- Set a new timer using window.setTimeout() to delay function execution.
- Invoke the original function using func.call(this, ...args) inside the timer.
- Test your debounce function with different debounce intervals and functions.
- Consider adding an optional parameter for immediate execution before the debounce interval.

**Solution: Implementing a Debounce Function in JavaScript**

**Explanation:**

1. The `debounce` function is designed to take in two parameters: `func` (the function to be debounced) and `wait` (the time interval in milliseconds).
2. Inside the `debounce` function, a variable named `timer` is declared and initialized with `null`. This variable will store the timer ID used for debouncing.

3. The `return` statement defines an inner function that will be returned by the `debounce` function. This inner function is the actual debounced function that will be called when the debounced action occurs.

4. Within the inner function:

   - The existing timer, if any, is cleared using `window.clearTimeout(timer)`. This ensures that any previous timers are canceled before setting a new one.

   - A new timer is set using `window.setTimeout()`. This timer will execute the `func` after the specified `wait` interval.

   - Inside the timer's callback function, the original `func` is called using `func.call(this, ...args)`. The `this` context and arguments (`...args`) are properly passed to the original function.

5. By using the `debounce` function, you can now control how frequently the `func` is executed, ensuring that it's called only after the user pauses between actions.

**Usage:**

To use the `debounce` function, you can do the following:

```javascript
// Create a debounced version of the function 'myFunction'
const debouncedFunction = debounce(myFunction, 500);

// Attach the debounced function to an event listener
element.addEventListener("input", debouncedFunction);
```

In the above code, the `myFunction` will be called only after the user stops typing for 500 milliseconds, thanks to the debounce mechanism provided by the `debounce` function.

**Solution:**

```javascript
// Complete the function below
function debounce(func, wait) {
  let timer = null; // Initialize the timer variable

  // Return the debounced function
  return function (...args) {
    // Clear any existing timer
    window.clearTimeout(timer);

    // Set a new timer to execute the function after the specified interval
    timer = window.setTimeout(() => {
      // Call the original function with the provided arguments and context
      func.call(this, ...args);
    }, wait);
  };
}
```
