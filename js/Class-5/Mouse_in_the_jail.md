**Raw Problem**

Write a JavaScript program to perform the following task:

You are given an empty cell.
Whenever the mouse enters the cell,
a jail should be drawn over it.
And it should be removed once it leaves.

**URL of the image:** https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/055/850/original/jail.jpg?1699030242

NOTE :
Here cursor is referred to as the mouse and the box as the empty cell.
To draw the jail:
Use the background image provided and set it as the background for the cell when the mouse enters the cell.

Use the below-mentioned method to set the image as background:
`element.style.background = url(image_src)`

**Hints**

- Add eventListener of 'mouseover' on the cell to draw the jail.
- Use `style->background` property to set the background image (draw jail).

- Add eventListener of 'mouseout' on the cell to remove the jail.
- Use `style->background` property to set the background as 'none' (remove jail).

**Solution Approach**
To add an event listener of 'mouseover' on a cell to draw a jail image and 'mouseout' to remove it, you can use the following approach:

First, use querySelector to select the cell element you want to add the event listener to.

Then, add an event listener of 'mouseover' to the cell element using addEventListener method.

Inside the 'mouseover' event listener function, use the style.background property to set the background image to the jail image.

Next, add an event listener of 'mouseout' to the cell element using addEventListener method.

Inside the 'mouseout' event listener function, use the style.background property to set the background to 'none' to remove the jail image.

**Solution**

```js
let cell = document.querySelector(".cell");

// 1. Add eventListener of 'mouseover' on the cell to draw the jail.
cell.addEventListener("mouseover", function () {
  // 2. Use style->background property to set the background image (draw jail).
  cell.style.background = "url(./jail.jpg)";
});

// 3. Add eventListener of 'mouseout' on the cell to remove the jail.
cell.addEventListener("mouseout", function () {
  // 4. Use style->background property to set the background as 'none' (remove jail).
  cell.style.background = "none";
});
```
