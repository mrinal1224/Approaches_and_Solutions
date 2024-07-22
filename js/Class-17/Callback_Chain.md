**Problem Description**
Write a function callbackChain that takes an array of functions as callbacks. The functions should be executed one after another in the order they are provided, with a delay of 500 milliseconds between each execution.

You need to implement the callbackChain function, which will execute a sequence of callback functions one after another with a delay of 500 milliseconds between each execution.

```javascript
function callbackChain(callbacks)
```

Example

```javascript
callbackChain([
  () => console.log("First callback"),
  () => console.log("Second callback"),
  () => console.log("Third callback"),
]);

// Output:
// Prints all three messages at 500 ms delay
```

**Hints**

```javascript
// Utilize a loop or recursion to iterate through the array of callbacks.
// Use the index of the array to calculate the delay.
```

**Solution Approach**

```javascript
// Iterate through the array of callback functions.
// Use setTimeout to introduce a delay of 500 milliseconds between each function execution.
```

**Solution**

```javascript
function callbackChain(callbacks) {
  let index = 0;

  function executeCallback() {
    if (index < callbacks.length) {
      callbacks[index]();
      index++;
      setTimeout(executeCallback, 500);
    }
  }

  executeCallback();
}
```
