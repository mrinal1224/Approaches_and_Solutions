**Problem Description**
Write a function that takes in an array of numbers and returns the maximum value in that array.

Example:

Input:
[1, 4, 2, 7, 5]

Output:
7

**Hints**
Make use of the `Math.max` method to find the maximum value in an array.

**Solution Approach**
Initialize a variable maxValue with the value of the first element of the array.
Traverse through the array.
If any element is greater than maxValue, update maxValue with that element's value.
Return maxValue

**Solution**

```javascript
function findMax(arr) {
  let maxValue = arr[0];
  for (let i = 1; i < arr.length; i++) {
    if (arr[i] > maxValue) {
      maxValue = arr[i];
    }
  }
  return maxValue;
}
```
