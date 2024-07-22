**Problem Description**

Write a function that calculates the sum of all numbers in an array.

Example:

Input:
[1, 2, 3, 4]

Output:
10

**Solution Approach**
Initialize a sum variable to 0.
Traverse the array, adding each number to the sum.
Return the sum.

**Solution**

```javascript
function sumOfArray(arr) {
  let sum = 0;
  for (let i = 0; i < arr.length; i++) {
    sum += arr[i];
  }
  return sum;
}
```
