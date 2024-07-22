**Problem Description**
Write a function delayedSum that takes two integers, a and b, and a callback function callback. The function should use setTimeout to delay calling the callback for 1000 milliseconds and then pass the sum of a and b as an argument to the callback.
You need to implement the delayedSum function, which will introduce a delay of 1000 milliseconds using setTimeout. After the delay, it should call the provided callback function with the sum of a and b.

```javascript
function delayedSum(a, b, callback)
```

Example

```javascript
delayedSum(3, 5, (result) => {
  console.log(result); // Expected output after 1000ms: 8
});
```

**Hints**

```javascript
// Utilize the setTimeout function to introduce the delay.
// Make use of arrow functions for concise code.
// Pay attention to the order of operations.
```

**Solution Approach**

```javascript
// Use setTimeout to introduce a delay of 1000 milliseconds.
// Calculate the sum of a and b.
// Call the provided callback function with the sum as an argument.
```

**Solution**

```javascript
function delayedSum(a, b, callback) {
  setTimeout(() => {
    const sum = a + b;
    callback(sum);
  }, 1000);
}
```
