**Raw Problem**
Write a polyfill of 'map'

You need to complete the function reduce, which receives 2 inputs:

1. 'arr'
   1.1. An array of numbers
2. 'callback'
   2.1. A function that takes a number as input, performs some mathematical operation on that number and returns the end value.
   2.2. callback(num) returns a new number.
   2.3. For each element of the input arr, you need to store the returned number in the answer. (mapped array)

The function map(arr, callback), when called, should behave in similar fashion as inbuilt Array.prototype.map() function in JavaScript.
Refrain from using the inbuilt Array.protoype.map() function in JS, trivial test case would check for that.

```

Example 1:
arr = [1, 2, 3, 4, 5];
callback = fn(num) => num * num;

Output:
[1, 4, 9, 16, 25]

Example 2:
arr = [1, 2, 3, 4, 5];
callback = fn(num) => num * 2;

Output:
[2, 4, 6, 8, 10]
```

**Hints**

1. Create an empty array called `mappedArray` to store the mapped values.
2. Use a loop to iterate over each element of the input array `arr`.
3. Inside the loop, apply the `callback` function to the current element and store the result in a variable, let's call it `result`.
4. Add the `result` to the `mappedArray` using the `push` method.
5. After iterating over all elements, return the `mappedArray` as the final result.

**Solution Approach**

1. Start by defining the `map` function that takes two parameters: `arr` (the input array) and `callback` (the function to be applied to each element).
2. Create an empty array called `mappedArray` to store the mapped values.
3. Use a `for` loop to iterate over each element of the input array `arr`.
4. Inside the loop, call the `callback` function with the current element as its argument and assign the result to a variable, let's call it `result`.
5. Append the `result` to the `mappedArray` using the `push` method, which adds the value to the end of the array.
6. Repeat steps 4-5 for each element in the input array until the loop is complete.
7. Once the loop finishes, return the `mappedArray` as the final result.
8. The `map` function is now complete.

**Solution**

```javascript
function map(arr, callback) {
  const mappedArray = [];
  for (let i = 0; i < arr.length; i++) {
    const result = callback(arr[i]);
    mappedArray.push(result);
  }
  return mappedArray;
}
```
