**Problem Description**
Write a function that takes in a string and returns the longest word in that string.
If there are multiple words with the same length, return the first one you encounter.

Example:

Input:

"JavaScript is a fun programming language"

Output:

"programming"

**Hints**
Make use of the `split` method to split the string into an array of words.

**Solution Approach**
Split the string into an array of words.
Initialize a variable to hold the longest word and set it to the first word in the array.
Traverse through the array. For each word, if its length is greater than the length of the longest word, update the longest word.
Return the longest word.

**Solution**

```javascript
function findLongestWord(str) {
  let words = str.split(" ");
  let longestWord = words[0];
  for (let i = 1; i < words.length; i++) {
    if (words[i].length > longestWord.length) {
      longestWord = words[i];
    }
  }
  return longestWord;
}
```
