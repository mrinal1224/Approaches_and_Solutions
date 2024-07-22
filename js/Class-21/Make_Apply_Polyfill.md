**Raw Problem**

**Write a polyfill for the apply method in JavaScript.**

You need to complete the function **applyPolyfill** which takes three inputs:

1. fn - A function on which apply method needs to be polyfilled.
2. context - The value of this to be used when calling the function.
3. args - An array of arguments to be passed to the function.

The function applyPolyfill(fn, context, args), when called, should behave in a similar fashion as the inbuilt Function.prototype.apply() function in JavaScript.  
Refrain from using the inbuilt Function.protoype.apply() function in JS, trivial test case would check for that.

**Example**:

```javascript
function greet(country) {

return 'Hello, ' + this.name + ' from '+ country;

}

const person = {

name: 'John',

};

const result = **applyPolyfill**(greet, person, \['India'\]);
console.log(result);


// **Output:**
// Hello, John! from India
```

**Hints**

1. The applyPolyfill function should accept three arguments: fn (the function), context (the context), and args (the arguments).
2. Inside the applyPolyfill function, you need to execute the original function with the specified context and arguments.
3. You can use the context argument to set the context (this) for the function.
4. You can use the args argument to pass the arguments to the function.

**Solution Approach**

1. Define the applyPolyfill function that takes three parameters: fn (the function), context (the context), and args (the arguments).
2. Inside the applyPolyfill function, execute the original function with the specified context and arguments.
3. Use the context argument to set the context (this) for the function.
4. Use the args argument to pass the arguments to the function.
5. The applyPolyfill function is now complete.

**Solution**

```javascript
function applyPolyfill(fn, context, args) {
  // Check if the fn is a function

  if (typeof fn !== "function") {
    throw new TypeError("fn must be a function");
  }

  // Set the context if it's null or undefined

  if (context == null) {
    context = window;
  }

  // Create a unique property on the context object to store the function

  const uniqueProp = Symbol("applyPolyfill");

  context[uniqueProp] = fn;

  // Call the function with the given context and arguments

  const result = context[uniqueProp](...args);

  // Delete the unique property from the context object

  delete context[uniqueProp];

  // Return the result

  return result;
}
```
