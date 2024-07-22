**Raw Problem**

**Write a polyfill of 'filter'**

You need to complete the function reduce, which receives 2 inputs:

1. 'arr'

   1.1. An array of numbers

2. 'callback'

   2.1. A function that does takes a number as input and returns a true or false value in return.

   2.2. callback(num) returns a boolean.

   2.3. For each element of the array, if returned boolean is:

   2.3.1. True: The element will be in the filtered array.

   2.3.2. False: The element will not be in the filtered array.

The function filter(arr, callback), when called, should behave in similar fashion as inbuilt Array.prototype.filter() function in JavaScript.  
Refrain from using the inbuilt Array.protoype.filter() function in JS, trivial test case would check for that.

**Example 1:**  
arr = [1, 2, 3, 4, 5];  
callback = fn(num) => num % 2 === 0;

**Output:**  
[2, 4]

**Example 2:**  
arr = [1, 2, 3, 4, 5];  
callback = fn(num) => num < 4;

**Output:**  
[1, 2, 3]

**Hints**

1. Create an empty array called `filteredArray` to store the filtered values.
2. Use a loop to iterate over each element of the input array `arr`.
3. Inside the loop, apply the `callback` function to the current element and check if the result is `true`.
4. If the result is `true`, add the current element to the `filteredArray` using the `push` method.

**Solution Approach**

1. Start by defining the `filter` function that takes two parameters: `arr` (the input array) and `callback` (the function to be applied to each element).
2. Create an empty array called `filteredArray` to store the filtered values.
3. Use a `for` loop to iterate over each element of the input array `arr`.
4. Inside the loop, call the `callback` function with the current element as its argument and check if the result is `true`.
5. If the result is `true`, append the current element to the `filteredArray` using the `push` method.
6. Repeat steps 3-5 for each element in the input array until the loop is complete.
7. Once the loop finishes, return the `filteredArray` as the final result.
8. The `filter` function is now complete.

**Solution**

```javascript
function filter(arr, callback) {
  const filteredArray = [];
  for (let i = 0; i < arr.length; i++) {
    if (callback(arr[i])) {
      filteredArray.push(arr[i]);
    }
  }
  return filteredArray;
}
```
