**Problem Description**
Write a function timeoutPromise that takes a delay time in milliseconds and returns a Promise. The Promise should resolve after the specified delay.
You need to implement the timeoutPromise function, which returns a Promise. The Promise should resolve after the specified delay time.

```javascript
function timeoutPromise(delay)
```

```javascript
// Test Cases
timeoutPromise(2000)
  .then((result) => console.log(result)) // Expected output after 2000ms: "Promise resolved after 2000 milliseconds"
  .catch((error) => console.error(error));
```

**Hints**

```javascript
// Utilize the Promise constructor and setTimeout.
// Remember that the resolve function can be called to fulfill the Promise.
```

**Solution Approach**

```javascript
// Use the Promise constructor to create a new Promise.
// Use setTimeout to introduce the specified delay.
// Resolve the Promise after the delay.
```

**Solution**

```javascript
function timeoutPromise(delay) {
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve(`Promise resolved after ${delay} milliseconds`);
    }, delay);
  });
}
```
