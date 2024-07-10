# Custom Greeting Component

Note : these questions will do string matching and to avoid confusion please write the exact text

## Problem Statement

Your task is to create a React component named Greeting with the following requirements:

1. The component should take two props, age and occupation.
2. Inside the component, use the provided template to display a greeting message. The message should include the `name` that shpuld be equal to `Jasbir` with `age` prop, and the provided `occupation` prop passed
3. Output should be

```jsx
<h1>
  Hello {name} Thanks Babel :) is {age} old and works as {occupation}{" "}
</h1>
```

Note : these questions will do string matching and to avoid confusion please write the exact text

## Complete Solution

```jsx
function Greeting(obj) {
  let { age, occupation } = obj;
  let name = "Jasbir";
  return (
    <h1>
      Hello {name} Thanks Babel :) is {age} old and works as {occupation}{" "}
    </h1>
  );
}

export default Greeting;
```

## Solution Approach

To address the task of creating a React component named `Greeting`, follow these steps:

1. **Define the Component:**
   Start by defining a function named `Greeting`. This function will be your React component. It should take a single argument, `props`, which represents the properties passed to the component when it is used.

2. **Destructure Props:**
   Inside the `Greeting` function, extract the `age` and `occupation` properties from the `props` object. This can be done using JavaScript's object destructuring syntax. These properties will be used to dynamically fill in the details of the greeting message.

3. **Hardcode the Name:**
   According to the problem statement, the name in the greeting message should always be `Jasbir`. Therefore, you can directly use this value in your JSX template without passing it as a prop.

4. **Create the JSX Template:**
   Return a JSX template from the `Greeting` function. This template should be an `<h1>` element containing the greeting message. Use curly braces `{}` to insert the JavaScript expressions for `name`, `age`, and `occupation` into the template.

5. **Ensure Exact Output Format:**
   Make sure the output of your JSX template matches the specified format exactly, including spaces and punctuation. The problem statement emphasizes string matching, indicating that the output should be identical to the expected result.

6. **Test the Component:**
   Use `ReactDOM.render` to test your `Greeting` component with different props to ensure it produces the correct output. This step will help verify that your component behaves as expected for various inputs.
