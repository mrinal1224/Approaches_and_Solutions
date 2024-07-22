**Problem Description**
Write a JavaScript function named findFirstNegative that finds and returns the first negative number in an array using the find() method.
return undefined if there are no negative numbers in the array.

Inputs:
An array of numbers.

Outputs:
A number representing the first negative number in the array or undefined if there are no negative numbers.

**Hints**
The find() method returns the value of the first element in the array that satisfies the provided testing function.

**Solution Approach**
Use the find() method and provide a callback that checks if the number is negative.

**Solution**

```javascript
function findFirstNegative(arr) {
  return arr.find((num) => num < 0);
}
```
