**Raw Problem**  
**Write a program in JavaScript,**  
that implements the following behaviour on the above p tags:

1. single clicking highlights them with red color
2. double clicking highlights them with green color
3. triple removes the highlights

**Note:**  
Here highlight means to set the background of the element to a desired color.

**Hints**
Multiple "p" tags will respond to clicks.  
Red, green, and no background on different clicks.  
Event details used to determine click count.  
Set background based on click count.

**Solution Approach**
Here's an explanation of the code snippet:

- The code selects all the HTML elements with the "p" tag (paragraphs) and assigns them to the variable `pTags` using the `document.querySelectorAll("p")` method.
- It then iterates through all the selected "p" elements using a for loop.
- For each paragraph element, a click event listener is added.
- When a click event occurs on a paragraph element, the event listener function is triggered.
- Inside the event listener function, the `e.detail` property is used to determine the click count (number of clicks) on the paragraph element.
- If `e.detail` is equal to 1 (single click), the background color of the clicked paragraph element (`e.currentTarget`) is set to "red".
- If `e.detail` is equal to 2 (double click), the background color of the clicked paragraph element is set to "green".
- If `e.detail` is equal to 3 (triple click), the background color of the clicked paragraph element is removed ("none").

**Solution**

```js
let pTags = document.querySelectorAll("p");

for (let i = 0; i < pTags.length; i++) {
  pTags[i].addEventListener("click", function (e) {
    if (e.detail == 1) e.currentTarget.style.background = "red";
    if (e.detail == 2) e.currentTarget.style.background = "green";
    if (e.detail == 3) e.currentTarget.style.background = "none";
  });
}
```
