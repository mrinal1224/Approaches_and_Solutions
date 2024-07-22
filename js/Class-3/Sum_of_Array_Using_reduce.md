**Problem Description**
Write a JavaScript function named sumArray that takes an array of numbers and returns the sum of all the numbers in the array using the reduce() method.

The tests also check whether the reduce() method has been used.

Example:

Input:
[1, 2, 3, 4]

Output:
10
reduce() is used.

**Hints**
The reduce() method applies a function against an accumulator and each element in the array (from left to right) to reduce it to a single value.

**Solution Approach**
Initialize the reduce() method with an initial accumulator value of 0. Then, for each value in the array, add it to the accumulator.

**Solution**

```javascript
function sumArray(arr) {
  return arr.reduce((acc, curr) => acc + curr, 0);
}
```
