**Problem Description**
Write a function that checks if a given string is a palindrome.
A palindrome is a word, phrase, number, or other sequences of characters which reads the same backward as forward (ignoring spaces, punctuation, and capitalization).

Example:

Input:
"Madam"

Output:
true

**Hints**
Make use of the `toLowerCase` method to convert the string to lowercase.

**Solution Approach**
Convert the string to lowercase.
Remove all non-alphanumeric characters.
Compare the string with its reverse.

**Solution**

```javascript
function isPalindrome(str) {
  str = str.toLowerCase().replace(/[^a-z0-9]/g, "");
  return str === str.split("").reverse().join("");
}
```
