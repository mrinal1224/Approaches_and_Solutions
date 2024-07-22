**Problem Description**
Write a JavaScript function named filterOutOdd that uses the filter() method to filter out odd numbers from an array.

Example:

Inputs:
An array of numbers.

Outputs:
An array of numbers without odd numbers.

**Hints**
Use the filter() method to create a new array with all elements that pass the test implemented by the provided function.

**Solution Approach**
Use the filter() method and provide a callback that checks if the number is even.

**Solution**

```javascript
function filterOutOdd(arr) {
  return arr.filter((num) => num % 2 === 0);
}
```
