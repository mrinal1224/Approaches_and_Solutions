**Raw Problem**

**Write a polyfill of 'reduce'**

You need to complete the function reduce, which receives 2 inputs:

1. 'arr'

   1.1. An array of numbers

2. 'reducer'

   2.1. A function that does some mathematical operation on 2 input numbers and returns the resultant.

   2.2. reducer(num1, num2) returns a resultant.

The function reduce(arr, reducer), when called, should behave in a similar fashion as the inbuilt Array.prototype.reduce() function in JavaScript.  
Refrain from using the inbuilt Array.prototype.reduce() function in JS, a trivial test case would check for that.

**Input :**  
arr = [2, 3, 4, 5]  
reducer = fn(a,b){ return a+b }

reduce(arr, reducer)

**Output :**  
14

**Input :**  
arr = [2, 3, 4]  
reducer = fn(a,b){ return a-b }

reduce(arr, reducer)

**Output :**  
-5

**Hints**

1. Create a variable `accumulator` to store the intermediate result.
2. Use a loop to iterate over each element of the input array `arr`.
3. Inside the loop, apply the `reducer` function to the current element and the `accumulator`.
4. Update the `accumulator` with the result of the `reducer` function.
5. After iterating over all elements, return the `accumulator` as the final result.

**Solution Approach**

1. Start by defining the `reduce` function that takes two parameters: `arr` (the input array) and `reducer` (the function to be applied to each element).
2. Create a variable `accumulator` to store the intermediate result.
3. Use a `for` loop to iterate over each element of the input array `arr`.
4. Inside the loop, call the `reducer` function with the current element and the `accumulator` as its arguments and update the `accumulator` with the result.
5. Repeat steps 3-4 for each element in the input array until the loop is complete.
6. Once the loop finishes, return the `accumulator` as the final result.
7. The `reduce` function is now complete.

**Solution**

```javascript
function reduce(arr, reducer) {
  let accumulator = arr[0];
  for (let i = 1; i < arr.length; i++) {
    accumulator = reducer(accumulator, arr[i]);
  }
  return accumulator;
}
```
