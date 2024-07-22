**Raw Problem**
You are tasked with creating a function `fn` that allows for function chaining and keeps track of the number of function calls made. Each time the function is called, it returns another function, and the count of function calls is incremented. The function chain can be terminated by passing a specific value.

### Constraints:

- The function chain can have an arbitrary number of function calls.
- The function chain is terminated by passing the value 0 to the innermost function.

### Examples:

### Example 1:

```javascript
fn()()()()(0);
```

#### Output:

```
4
```

### Example 2:

```javascript
fn()()()(0);
```

#### Output:

```
3
```

### Example 3:

```javascript
fn()()()()()(0);
```

#### Output:

```
5
```

**Hints**

1.  The function fn should return another function each time it is called.
2.  You need a variable to keep track of the count of function calls. Consider using a closure to maintain the count across multiple calls.
3.  The inner function should increment the count each time it is invoked, except when the argument passed to it is 0.
4.  When the termination condition is met (argument is 0), return the current count value.

**Solution Approach**

1.  Start by defining the function fn. Inside fn, initialize a count variable with an initial value of 1.
2.  Create an inner function, let's call it innerFn, within fn. This inner function will be returned by fn.
3.  Implement innerFn such that it checks if the argument passed to it is 0. If it is, return the current count value.
4.  If the argument is not 0, increment the count variable by 1 and return innerFn itself.
5.  Make sure to update the count variable within the scope of fn and maintain its value across multiple calls to innerFn.
6.  Return innerFn from fn.
7.  Test the function by calling fn and chaining multiple function calls. Pass 0 as the argument to the innermost function to terminate the chain and obtain the count value.

**Solution**

```javascript
function fn() {
  let count = 1;

  function innerFn(value) {
    if (value === 0) {
      return count;
    } else {
      count++;

      return innerFn;
    }
  }

  return innerFn;
}
```
