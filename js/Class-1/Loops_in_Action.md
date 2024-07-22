**Problem Description**
Use a for loop to iterate through an array of numbers and log each element multiplied by 2.

main function will be called with an array of integers as argument.

Input Format
Values of an array

Constraints
n <= 10 ^ 9

Output Format
Logged Integers

Sample Input 0
[1, 2, 3]

Sample Output 0
2
4
6

**Hints**
Use a for loop to iterate through the array and log each element multiplied by 2.

**Solution**

```js
function main(arr) {
  for (let i = 0; i < arr.length; i++) {
    console.log(arr[i] * 2);
  }
}
```
