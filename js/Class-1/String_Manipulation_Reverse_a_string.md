**Problem Description**

Create a function called reverseString that takes a string as input and returns the reversed version.

The function is called with the argument of a string that needs to be reversed.
Use array methods to reverse the string.

Input Format
String

Sample Input 0
hello

Sample Output 0
olleh

**Hints**

- Use the split method to convert the string into an array.
- Use the reverse method to reverse the array.
- Use the join method to convert the array back to a string.

**Solution**

```js
function reverseString(str) {
  return str.split("").reverse().join("");
}
```
