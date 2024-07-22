**Problem Description**
Write a function named calculateArea that takes the radius of a circle as a parameter and returns the area.
The calculateArea function is called with the argument and the result is stored in a variable called circleArea.

Input Format
Number

Constraints
n <= 10 ^ 9

Output Format
Number

Sample Input 0
5

Sample Output 0
78.5

**Hints**
Use the formula for the area of a circle: area = 3.14 \* radius^2.

**Solution**

```js
function calculateArea(radius) {
  return 3.14 * radius * radius;
}
```
