**Raw Problem**

Implement key taps such that on:

1. Pressing `1` you scroll to section 1,
2. Pressing `2` you scroll to section 2, and
3. Pressing `3` you scroll to section 3.
4. Also implement key tap `b` to go to the bottom of the page.
5. And key tap `t` to go to the top of the page.

**Note:**  
Write code in the `script.js` file.

_Click on the folder icon to access the script.js file_

![script-access](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/055/784/original/script-access.PNG?1699006952)

**Hints**

Here are some hints to implement the functionality:

1. Use `document.querySelector` to select the relevant HTML elements that correspond to the sections you want to scroll to (e.g., s1, s2, s3).
2. Add an event listener to the `document` to listen for keydown events. You can identify the key pressed using the event object (e.g., `e.key`) to determine which action to perform.
3. For scrolling to specific sections, consider using the `scrollIntoView` method on the selected elements. You may want to wrap these operations in conditional statements to handle different key presses.
4. To scroll to the bottom of the page, you can use `window.scrollBy` with a positive value to scroll downwards.
5. To scroll to the top of the page, you can use `window.scrollBy` with a negative value to scroll upwards.

By implementing these hints, you can create a solution that responds to key presses and scrolls to the desired sections or positions on the page.

**Solution Approach**
Here's a step-by-step approach with code snippets to implement the functionality of scrolling to sections on keypress (1, 2, 3), scrolling to the bottom of the page (b), and scrolling to the top of the page (t):

1. Select the relevant HTML elements for the sections you want to scroll to (e.g., s1, s2, s3) and store them in variables.

```javascript
const s1 = document.querySelector("#s1");
const s2 = document.querySelector("#s2");
const s3 = document.querySelector("#s3");
```

2. Add an event listener to the `document` to listen for keydown events.

```javascript
document.addEventListener("keydown", function (e) {
  // Handle key presses here
});
```

3. Inside the event listener function, use conditional statements to check which key was pressed (1, 2, 3, b, or t).

```javascript
document.addEventListener("keydown", function (e) {
  if (e.key === "1") {
    // Scroll to section 1 (s1)
  } else if (e.key === "2") {
    // Scroll to section 2 (s2)
  } else if (e.key === "3") {
    // Scroll to section 3 (s3)
  } else if (e.key === "b") {
    // Scroll to the bottom of the page
  } else if (e.key === "t") {
    // Scroll to the top of the page
  }
});
```

4. Implement scrolling logic for each condition. Use the `scrollIntoView` method to scroll to specific sections or `window.scrollBy` to scroll to the bottom or top of the page.

```javascript
document.addEventListener("keydown", function (e) {
  if (e.key === "1") {
    s1.scrollIntoView({ behavior: "smooth" }); // Scroll to section 1 smoothly
  } else if (e.key === "2") {
    s2.scrollIntoView({ behavior: "smooth" }); // Scroll to section 2 smoothly
  } else if (e.key === "3") {
    s3.scrollIntoView({ behavior: "smooth" }); // Scroll to section 3 smoothly
  } else if (e.key === "b") {
    window.scrollBy(
      0,
      document.querySelector("html").getBoundingClientRect().height
    );
  } else if (e.key === "t") {
    window.scrollBy(
      0,
      -document.querySelector("html").getBoundingClientRect().height
    );
  }
});
```

5. Customize the scrolling behavior by adjusting options such as `behavior` for smooth scrolling.

By following these steps, you can create a solution that allows users to scroll to specific sections and navigate to the top or bottom of the page using keyboard inputs.

**Solution**

```javascript
let s1 = document.querySelector("#s1");
let s2 = document.querySelector("#s2");
let s3 = document.querySelector("#s3");
document.addEventListener("keydown", function (e) {
  if (e.key == 1) {
    s1.scrollIntoView();
  } else if (e.key == 2) {
    s2.scrollIntoView();
  } else if (e.key == 3) {
    s3.scrollIntoView();
  } else if (e.key == "b") {
    window.scrollBy(
      0,
      document.querySelector("html").getBoundingClientRect().height
    );
  } else if (e.key == "t") {
    window.scrollBy(
      0,
      -document.querySelector("html").getBoundingClientRect().height
    );
  }
});
```
