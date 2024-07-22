**Problem Description**
Write a function that takes in a string and returns the count of vowels in that string.
Consider the vowels to be a, e, i, o, u (both uppercase and lowercase).

Example:

Input:
"Hello World"
Output:
3 (Because there are 2 'o's and 1 'e')

**Hints**
Make use of the `includes` method to check if a character is a vowel or not.

**Solution Approach**

1. Initialize a counter to zero.
2. Traverse through each character in the string.
3. If the character is a vowel, increase the counter.
4. Return the counter.

**Solution**

```javascript
function countVowels(str) {
  let vowels = "aeiouAEIOU";
  let count = 0;
  for (let i = 0; i < str.length; i++) {
    if (vowels.includes(str[i])) {
      count++;
    }
  }
  return count;
}
```
