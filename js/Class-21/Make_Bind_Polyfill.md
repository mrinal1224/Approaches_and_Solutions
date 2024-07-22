**Raw Problem**

**Write a polyfill for the bind method in JavaScript.**

You need to create a polyfill for the bind method, which allows you to set the context (the value of this) for a function and optionally preset some initial arguments.

You should implement a **function customBind** on the Function.prototype object. This function should accept a single argument obj, which represents the context (the value of this) to be used when calling the function.

When the customBind method is called on a function, it should return a new function that, when invoked, executes the original function with the specified context (obj) and any additional arguments passed to the bound function.

Your task is to complete the implementation of the customBind function.

**Example:**

```javascript
function greet() {
  return "Hello, " + this.name + "!";
}

const person = {
  name: "John",
};

const boundFunction = greet.customBind(person);
const result = boundFunction();
console.log(result);

// **Output:**
// Hello, John!
```

**Hints**

1. The customBind method should be added to the Function.prototype object.
2. The customBind method should accept a single argument obj (the context).
3. Inside the customBind method, you need to return a new function that executes the original function with the specified context and any additional arguments.
4. You can use the obj argument to set the context (this) for the function.
5. You can use the rest parameter syntax to capture any additional arguments passed to the bound function.

**Solution Approach**

1. Define the customBind method on the Function.prototype object.
2. The customBind method should accept a single argument obj (the context).
3. Inside the customBind method, return a new function that executes the original function with the specified context and any additional arguments.
4. Use the obj argument to set the context (this) for the function.
5. Use the rest parameter syntax to capture any additional arguments passed to the bound function.
6. The customBind method is now complete.

**Solution**

```javascript
Function.prototype.customBind = function (obj) {
  obj.fnRef = this;

  return function (...args) {
    return obj.fnRef(...args);
  };
};
```
