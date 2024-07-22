**Raw Problem**  
Write a program in JavaScript to do the below-mentioned task:  
Fix the mathematical problem. '2 + 2 = 22' to '2 + 2 = 4'  
NOTE:  
Using JS only change the **innerText** property of the target element containing the equation

**Hints**
Use querySelector to select the element  
Use innerText property to change the equation to '2 + 2 = 4'

**Solution Approach**
To use querySelector to select an element and change its inner text, you can use the following approach:

First, use querySelector to select the element you want to change.

Then, use the innerText property to change the text content of the element to the desired value.

Code :

**Solution**

```js
let p = document.querySelector("p");
// Use innerText property to change the equation to '2 + 2 = 4'
p.innerText = "2 + 2 = 4";
```
