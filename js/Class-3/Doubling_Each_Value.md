**Problem Description**
Write a JavaScript function named doubleValues that takes an array of numbers and returns a new array where each number is doubled using the map() method.

Inputs:
An array of numbers.

Outputs:
An array of numbers where each number is doubled.

**Hints**
The map() method creates a new array with the results of calling a function for every array element.

**Solution Approach**
Use the map() method to iterate over each value and double it.

**Solution**

```javascript
function doubleValues(arr) {
  return arr.map((num) => num * 2);
}
```
