**Raw Problem**

**Write a polyfill for the call method in JavaScript.**

You need to create a polyfill for the call method, which allows you to invoke a function with a specified context and any number of arguments.

Your task is to implement a function **customCall** on the Function.prototype object. This function should accept two or more arguments: obj, which represents the context (the value of this) to be used when calling the function, and ...args, which represents the arguments to be passed to the function.

When the customCall method is called on a function, it should execute the original function with the specified context (obj) and the provided arguments (args).

Your implementation should not rely on the inbuilt call method in JavaScript.

**Note**: Avoid using the inbuilt call method in JavaScript, as trivial test cases will check for that.

**Example:**

```javascript
function greet() {

return 'Hello, ' + this.name + '!';

}

const person = {

name: 'John',

};

const result = greet.**customCall**(person);
console.log(result);

// **Output**:
// Hello, John!
```

**Hints**

1. The customCall method should be added to the Function.prototype object.
2. The customCall method should accept two or more arguments: obj (the context) and ...args (the arguments).
3. Inside the customCall method, you need to execute the original function with the specified context and arguments.
4. You can use the obj argument to set the context (this) for the function.
5. You can use the ...args argument to pass the arguments to the function.

**Solution Approach**

1. Define the customCall method on the Function.prototype object.
2. The customCall method should accept two or more arguments: obj (the context) and ...args (the arguments).
3. Inside the customCall method, execute the original function with the specified context and arguments.
4. Use the obj argument to set the context (this) for the function.
5. Use the ...args argument to pass the arguments to the function.

**Solution**

```javascript
Function.prototype.customCall = function (obj, ...args) {
  // Execute the original function with the specified context and arguments
  return this.apply(obj, args);
};
```
