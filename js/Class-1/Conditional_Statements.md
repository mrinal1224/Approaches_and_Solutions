**Problem Description**
Write an if-else statement to check if a user is older than 18.
If true, log "You are an adult." otherwise log "You are a minor."

main function will be called with an argument with the value of age.

Input Format
Integer

Constraints
n <= 10 ^ 9

Output Format
String

Sample Input 0
12

Sample Output 0
You are a minor.

**Hints**
Use the if-else statement to check the age of the user.

**Solution**

```js
function main(age) {
  if (age > 18) {
    console.log("You are an adult.");
  } else {
    console.log("You are a minor.");
  }
}
```
