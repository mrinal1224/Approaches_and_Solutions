**Problem Statement**

> `Promise.any()` takes an iterable of elements (usually `Promises`). It returns a single promise that resolves as soon as any of the elements in the iterable fulfills, with the value of the fulfilled promise. If no promises in the iterable fulfill (if all of the given elements are rejected), then the returned promise is rejected with an [`AggregateError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError), a new subclass of Error that groups together individual errors.

> If an empty iterable is passed, then the promise returned by this method is rejected synchronously. The rejected reason is an `AggregateError` object whose errors property is an empty array.

_Source: [Promise.any() - JavaScript | MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/any)_

Let's implement our own version of `Promise.any()`, a `promiseAny` function, with the difference being the function takes in an array instead of an iterable and `AggregateError`s returned just have to return an array of error reasons, the message doesn't have to be set. Refer to the `AggregateError` constructor [examples on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/AggregateError/AggregateError).

Be sure to read the description carefully and implement accordingly!

**Examples**

**Example 1**

```javascript
const p0 = Promise.resolve(42);
const p1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve(21);
  }, 100);
});

await promiseAny([p0, p1]); // 42
```

**Example 2**

```javascript
const p0 = new Promise((resolve) => {
  setTimeout(() => {
    resolve(42);
  }, 100);
});

const p1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    reject("Err!");
  }, 400);
});

await promiseAny([p0, p1]); // 42
```

**Example 3**

```javascript
const p0 = Promise.reject("p0");
const p1 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("p1");
  }, 100);
});
const p2 = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("p2");
  }, 20);
});

const ans = await promiseAny([p0, p1, p2]);

console.log(ans); // p2
```

**Hints**

**Hint 1: Function Signature**

- Begin by defining the function `promiseAny` that takes an iterable as its input.

**Hint 2: Create a New Promise**

- Inside the `promiseAny` function, create a new Promise. This Promise will eventually resolve or reject based on the resolution of the input promises.

**Hint 3: Handle the Empty Iterable Case**

- Check if the input iterable is empty. If it is, reject the Promise with an `AggregateError` that contains an empty array of errors.

**Hint 4: Initialize Counters and Error Array**

- Initialize variables to track the number of pending promises (`pending`) and an array (`errors`) to store errors corresponding to each promise.

**Hint 5: Iterate Through the Iterable**

- Use a loop, such as `forEach`, to iterate through the promises in the iterable.

**Hint 6: Resolve on First Fulfillment**

- Inside the loop, attach a `then` handler to each promise. When a promise fulfills (resolves), resolve the new Promise with its value. You only need one promise to fulfill for the `promiseAny` to resolve.

**Hint 7: Track Errors and Pending Promises**

- If a promise rejects, capture the reason (error) and its index in the `errors` array. Decrease the `pending` count since that promise has been handled.

**Hint 8: Reject with AggregateError on All Rejections**

- After each promise is handled (either fulfilled or rejected), check if all promises have been handled (i.e., `pending` is zero). If all promises have been handled, reject the new Promise with an `AggregateError` that contains the array of captured errors.

With these hints, you can implement the `promiseAny` function, which resolves as soon as any of the input promises resolve and rejects with an `AggregateError` if all input promises reject.

**Solution Approach**

**Step 1: Define the Function Signature**

- Start by defining the `promiseAny` function, which takes an iterable as its input.

```javascript
function promiseAny(iterable) {
  // Implement the function here
}
```

**Step 2: Create a New Promise**

- Inside the `promiseAny` function, create a new Promise. This Promise will eventually resolve or reject based on the resolution of the input promises.

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    // Implement the function here
  });
}
```

**Step 3: Handle the Empty Iterable Case**

- Check if the input iterable is empty. If it is, reject the Promise with an `AggregateError` that contains an empty array of errors. This handles the case when there are no promises to resolve.

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    if (iterable.length === 0) {
      reject(new AggregateError([])); // Handle empty iterable case
    }
    // Continue with implementation
  });
}
```

**Step 4: Initialize Counters and Error Array**

- Initialize variables to track the number of pending promises (`pending`) and an array (`errors`) to store errors corresponding to each promise. These counters will help keep track of the status of the promises.

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    if (iterable.length === 0) {
      reject(new AggregateError([])); // Handle empty iterable case
    }

    let pending = iterable.length;
    const errors = new Array(iterable.length);
    // Continue with implementation
  });
}
```

**Step 5: Iterate Through the Iterable**

- Use a loop, such as `forEach`, to iterate through the promises in the iterable.

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    if (iterable.length === 0) {
      reject(new AggregateError([])); // Handle empty iterable case
    }

    let pending = iterable.length;
    const errors = new Array(iterable.length);

    iterable.forEach((item, index) => {
      // Continue with implementation for each promise in the iterable
    });
  });
}
```

**Step 6: Resolve on First Fulfillment**

- Inside the loop, attach a `then` handler to each promise. When a promise fulfills (resolves), resolve the new Promise with its value. You only need one promise to fulfill for the `promiseAny` to resolve, so no need to wait for others to complete.

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    if (iterable.length === 0) {
      reject(new AggregateError([])); // Handle empty iterable case
    }

    let pending = iterable.length;
    const errors = new Array(iterable.length);

    iterable.forEach((item, index) => {
      Promise.resolve(item).then(
        (value) => {
          resolve(value); // Resolve with the first fulfillment
        },
        (reason) => {
          // Continue with error handling
        }
      );
    });
  });
}
```

**Step 7: Track Errors and Pending Promises**

- If a promise rejects, capture the reason (error) and its index in the `errors` array. Decrease the `pending` count since that promise has been handled.

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    if (iterable.length === 0) {
      reject(new AggregateError([])); // Handle empty iterable case
    }

    let pending = iterable.length;
    const errors = new Array(iterable.length);

    iterable.forEach((item, index) => {
      Promise.resolve(item).then(
        (value) => {
          resolve(value); // Resolve with the first fulfillment
        },
        (reason) => {
          errors[index] = reason; // Capture errors
          pending--;

          if (pending === 0) {
            // Continue with rejection when all promises have been handled
          }
        }
      );
    });
  });
}
```

**Step 8: Reject with AggregateError on All Rejections**

- After each promise is handled (either fulfilled or rejected), check if all promises have been handled (i.e., `pending` is zero). If all promises have been handled, reject the new Promise with an `AggregateError` that contains the array of captured errors. This ensures that if none of the input promises fulfill, the `promiseAny` function rejects with all the captured errors.

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    if (iterable.length === 0) {
      reject(new AggregateError([])); // Handle empty iterable case
    }

    let pending = iterable.length;
    const errors = new Array(iterable.length);

    iterable.forEach((item, index) => {
      Promise.resolve(item).then(
        (value) => {
          resolve(value); // Resolve with the first fulfillment
        },
        (reason) => {
          errors[index] = reason; // Capture errors
          pending--;

          if (pending === 0) {
            reject(new AggregateError(errors)); // Reject with AggregateError if all promises reject
          }
        }
      );
    });
  });
}
```

With this detailed approach and code, you can implement the `promiseAny` function, which resolves as soon as any of the input promises resolve and rejects with an `AggregateError` if all input promises reject.

**Solution**

```javascript
function promiseAny(iterable) {
  return new Promise((resolve, reject) => {
    if (iterable.length === 0) {
      reject(new AggregateError([]));
    }

    let pending = iterable.length;
    const errors = new Array(iterable.length);
    iterable.forEach((item, index) =>
      Promise.resolve(item).then(
        (value) => {
          resolve(value);
        },
        (reason) => {
          errors[index] = reason;
          pending--;
          if (pending === 0) {
            reject(new AggregateError(errors));
          }
        }
      )
    );
  });
}
```
