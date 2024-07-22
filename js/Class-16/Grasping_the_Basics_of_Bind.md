**Problem Description**
You've just started learning about JavaScript functions and want to practice using the bind method.
Create a function, basicBind, that takes an object and a string. Your goal is to use the bind method to create a new function with the provided object as the context and the string as a pre-set argument.

```javascript
function basicBind(obj, str) {
  // Define a simple function
  function simpleFunction(arg1, arg2) {
    return this.value + arg1 + arg2;
  }

  // Use bind to create a new function with the specified context and pre-set argument

  // Call the bound function with the second argument
}

// Test Cases

const testObject = { value: "Learning JavaScript" };
console.log(basicBind(testObject, "Programming")); // Output: Learning JavaScriptProgramming is fun!
```

**Hints**
Use the bind method to create a new function with the specified context and pre-set argument.
Call the bound function with the second argument to get the final result.

**Solution Approach**
Create a simple function that takes two arguments and returns the sum of the context value and the arguments.
Use the bind method to create a new function with the specified context and pre-set argument.
Call the bound function with the second argument to get the final result.

**Solution**

```javascript
function basicBind(obj, str) {
  // Define a simple function
  function simpleFunction(arg1, arg2) {
    return this.value + arg1 + arg2;
  }

  // Use bind to create a new function with the specified context and pre-set argument
  const boundFunction = simpleFunction.bind(obj, str);

  // Call the bound function with the second argument
  return boundFunction(" is fun!", "");
}

// Test Cases

const testObject = { value: "Learning JavaScript" };
console.log(basicBind(testObject, "Programming")); // Output: Learning JavaScriptProgramming is fun!
```
