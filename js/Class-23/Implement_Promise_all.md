**Raw Problem**
The Promise.all() method takes an iterable of promises as an input, and returns a single Promise that resolves to an array of the results of the input promises
Could you write your own all() ? which should works the same as Promise.all()

note

Do not use Promise.all() directly, it is not helping

Function signature is given below, here promises parameter would contain an array of promises.

```javascript
all(promises);
```

**Examples**

**Example 1**

```javascript
let ans = "";
all([
  Promise.resolve((ans += `func1 `)),
  Promise.resolve((ans += `func2 `)),
  Promise.resolve((ans += `func3 `)),
]);
console.log(ans);
```

**Output**

```
func1 func2 func3
```

**Example 2**

```javascript
let ans = "";
let func1 = () => {
  setTimeout(() => {
    ans += `setTimeout called for func1\n`;
  }, 100);
};
let func2 = () => {
  setTimeout(() => {
    ans += `setTimeout called for func2\n`;
  }, 200);
};
let func3 = () => {
  setTimeout(() => {
    ans += `setTimeout called for func3\n`;
  }, 300);
};

all([func1(), func2(), func3()]);

setTimeout(() => {
  console.log(ans);
}, 500);
```

**Output**

```
setTimeout called for func1
setTimeout called for func2
setTimeout called for func3

```

**Example 2**

```javascript
let i = 1;
let ans = "";
let func1 = () => {
  setTimeout(() => {
    ans += `setTimeout called for func${i++} \n `;
  }, Math.random * 100);
};

all([func1(), func2(), func3()]);

setTimeout(() => {
  console.log(ans);
}, 500);
```

**Output**

```
setTimeout called for func1
setTimeout called for func2
setTimeout called for func3

```

**Hints**

- The all function takes an array of promises as its input.
- It returns a new Promise that will eventually resolve to an array of results once all the input promises have resolved or reject with an error if any of the input promises reject.
- Inside the all function, it initializes an empty array called results to store the results of the promises.
- It also tracks the number of promises that have completed using completedCount and the total number of promises in the input array with promisesCount.
- The function then iterates through the input promises using forEach and attaches a then handler to each promise.
- When a promise resolves, the result is stored in the results array at the corresponding index. The completedCount is incremented.
- If the completedCount reaches the total number of promises (promisesCount), it means that all promises have resolved. In this case, the new Promise is resolved with the results array.
- If any of the promises reject, the reject function is called with the error, and the new Promise is rejected with that error.

**Solution Approach**

```
Here is an implementation of all() function:

function all(promises) {
  return new Promise((resolve, reject) => {
    const results = [];
    let completedCount = 0;
    const promisesCount = promises.length;

    promises.forEach((promise, index) => {
      Promise.resolve(promise).then(
        (result) => {
          results[index] = result;
          completedCount += 1;
          if (completedCount === promisesCount) {
            resolve(results);
          }
        },
        (error) => {
          reject(error);
        }
      );
    });
  });
}
```

The function takes an array of promises as an input and returns a new Promise object that resolves to an array of results when all the input promises have resolved. It works by iterating through the input promises and attaching a then() handler to each one. When a promise resolves, its result is saved in the results array at the corresponding index. The completedCount is incremented, and when it reaches the total number of promises, the resolve() function of the new Promise object is called with the results array. If any of the promises reject, the reject() function of the new Promise object is called with the error.

**Solution**

```javascript
function all(promises) {
  // your code here
  return new Promise((resolve, reject) => {
    const result = [];

    if (promises.length === 0) {
      resolve(result);
      return;
    }

    let countPending = promises.length;

    promises.forEach((promise, index) => {
      Promise.resolve(promise).then((value) => {
        result[index] = value;
        countPending--;
        if (countPending === 0) {
          resolve(result);
        }
      }, reject);
    });
  });
}
```
