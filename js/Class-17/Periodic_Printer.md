**Problem Description**
Write a function periodicPrinter that takes a callback function and an interval timeInterval in milliseconds. The function should use setInterval to call the callback function every timeInterval milliseconds until explicitly stopped.  
You need to implement the periodicPrinter function, which will use setInterval to repeatedly print the provided message at the specified time interval until stopped.

Note: Please make sure to return the intervalId from the function, or else the code would never terminate from backend, resulting in failed testcase.
`javascript function periodicPrinter(callback, timeInterval) `
**Example**
`javascript periodicPrinter(() => { console.log("This is callback"); }, 1000); Output: Prints "This is callback" at every 1000ms until terminated by backend using clearInterval. (please reutn intervalID from the function) `

**Hints**

```javascript
// Utilize the setInterval function to execute a given function at regular intervals.
// Use a variable to keep track of the interval ID.
// To stop the periodic printing, you can use clearInterval and provide the interval ID.
```

**Solution Approach**

```javascript
// Use setInterval to repeatedly execute a function.
// The function should print the provided message.

// The above steps along with hints should help you understand the solution code.
```

**Solution**

```javascript
function periodicPrinter(callback, timeInterval) {
  const intervalId = setInterval(() => {
    callback();
  }, timeInterval);

  return intervalId;
}
```
