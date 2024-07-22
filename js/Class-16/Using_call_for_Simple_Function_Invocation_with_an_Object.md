**Problem Description**
Create a function greet that takes a parameter and returns a greeting message.
You are provided with an object contextObject with a name property.
Use the call method to invoke the greet function with contextObject as the context and generate a personalized greeting. Store the resultant string from the call function in personalizedGreeting variable.

Test case

```javascript
function greet(name) {
    return `Hello, ${name}!`;
  }

  // Object with a name property
  const contextObject = {
    name: "Alice"
  };

  // Test case using call
  const personalizedGreeting; // Write the function using call

  console.log(personalizedGreeting); // Output: Hello, Alice!
```

**Hints**
Use the call method to invoke a function with a specific context.
Use the object properties to pass the required arguments to the function.

**Solution Approach**
Create a function greet that takes a parameter and returns a greeting message.
Create an object contextObject with a name property.
Use the call method to invoke the greet function with contextObject as the context and generate a personalized greeting.

**Solution**

```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

// Object with a name property
const contextObject = {
  name: "Alice",
};

// Test case using call
const personalizedGreeting = greet.call(contextObject, contextObject.name);

console.log(personalizedGreeting); // Output: Hello, Alice!
```
