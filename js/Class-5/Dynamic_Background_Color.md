**Raw Problem**

Without using media queries do the following things:

1. For desktop sizes, i.e. `window.innerWidth > 1024`, make the background of the above div 'red'
2. For tablet sizes, i.e. `window.innerWidth > 600 & <= 1024`, make the background of the above div 'blue'
3. For mobile sizes, i.e. `window.innerWidth <= 600`, make the background of the above div 'green'

**Note:**  
Please use JS to enable the above feature whenever the window resizes.

_Online IDE might not show changes when resized due to its limitations. Use your local IDE to test your code before submitting._  
_Submissions would work if the code is correct._

**Hints**

Here are some hints and steps to help you write the code:

1. Start by selecting the target HTML element (in this case, a `div` element) using the DOM API.
2. Attach an event listener to the window object for the "resize" event. This will allow you to respond to changes in the window size.
3. Inside the event listener, check the `window.innerWidth` to determine the width of the window after the resize event.
4. Depending on the window width, update the style of the selected `div` element to change its background color. You can use conditional statements (if-else) to handle different width ranges.
5. Make sure to consider different width ranges and choose appropriate background colors for the `div` element.

Remember to structure your code and use JavaScript functions and event handling to make it clean and maintainable.

**Solution Approach**
Here's a step-by-step approach with code snippets:

1. First, select the target `div` element and define your event listener function.

```javascript
const div = document.querySelector("div");

function handleResize() {
  // Add code here to change the background color based on window.innerWidth
}
```

2. Inside the `handleResize` function, you can access the `window.innerWidth` property to determine the width of the window.

```javascript
function handleResize() {
  const windowWidth = window.innerWidth;
  // Add code here to change the background color based on windowWidth
}
```

3. Next, use conditional statements (if-else) to change the background color of the `div` element based on the window width.

```javascript
function handleResize() {
  const windowWidth = window.innerWidth;

  if (windowWidth <= 600) {
    div.style.background = "green";
  } else if (windowWidth <= 1024) {
    div.style.background = "blue";
  } else {
    div.style.background = "red";
  }
}
```

4. To complete the setup, add an event listener for the "resize" event on the `window` object and call the `handleResize` function when the event is triggered.

```javascript
window.addEventListener("resize", handleResize);
```

The code above listens for the "resize" event, and when the event is triggered, it calls the `handleResize` function, which updates the `div` element's background color based on the window width.

Make sure to place this code within an HTML document and include it after the `div` element you want to target. Additionally, you can further enhance the code by debouncing the event handler to avoid excessive function calls during rapid window resizing, but the above steps provide a basic working solution.

**Solution**

```javascript
let div = document.querySelector("div");

window.addEventListener("resize", function () {
  console.log(1);
  if (window.innerWidth <= 600) {
    div.style.background = "green";
  } else if (window.innerWidth <= 1024) {
    div.style.background = "blue";
  } else {
    div.style.background = "red";
  }
});
```
