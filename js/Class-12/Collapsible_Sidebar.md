**Raw Problem**

**Problem Description:**
Designers and developers often incorporate collapsible sidebars in web applications to make efficient use of screen real estate. This feature is particularly useful for applications with numerous options or tools that users don't need to access all the time.

## Your Task

Your task is to implement a collapsible sidebar for a web application.

Here is an example of what it should look like:

![](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/057/583/original/sidebar.gif?1700646300)

## Requirements

- You have two main `div` elements provided in the HTML: a sidebar (`#sidebar`) and a main content area (`#main-content`).
- The sidebar should start fully expanded with a width of `250px`. The main content should be displayed to the right, filling the rest of the viewport width.
- Include a button (`#toggle-button`) within the sidebar that will toggle its expanded and collapsed states.
- The sidebar should collapse to a width of `80px` when the toggle button is clicked and expand back to `250px` when clicked again.
- The main content area should adjust its position so it's always visible and using the available space next to the sidebar (it should have a padding of `80px`).
- Apply CSS to enhance the visual appearance according to the specifications given.

## Specifications

- The sidebar should have a background color of `#34495e` and contain white text. It should also have a padding of `15px 30px`
- The toggle button should have a background color of `#e74c3c`, which changes to `#c0392b` when hovered over.
- The main content area should have a background color of `#f1c40f`.

## Instructions for Implementation

- Write JavaScript code in `script.js` to add the toggle functionality to the sidebar.
- Write CSS in `style.css` to style the sidebar, the toggle button, and the main content area according to the given specifications.
- Ensure the main content area adjusts its position dynamically when the sidebar is toggled.

## Example Behavior

- Initially, the sidebar is fully expanded with a width of `250px`.
- Clicking the `#toggle-button` collapses the sidebar to `80px`, allowing the main content area to use the additional space.
- Clicking the `#toggle-button` again expands the sidebar back to `250px`.

**Hints**

1. Attach an event listener to the #toggle-button to listen for the 'click' event.
2. Within the event handler, you need to toggle classes on both #sidebar and #main-content to adjust their widths.
3. You can use the classList.toggle() method to add or remove a class from an element.
4. Ensure you've set up the required CSS transitions and styles for a smooth user experience.

**Solution Approach**

1. Select the toggle button element using its ID.
2. Attach a 'click' event listener to the button.
3. Within the event handler, toggle classes on both the sidebar and the main content divs to adjust their dimensions.
4. Implement CSS styles to visually handle the class changes, especially focusing on width, margin-left, and transitions.

**Solution**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Collapsible Sidebar Challenge</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      overflow: hidden;
    }

    #sidebar {
      position: fixed;
      width: 250px;
      height: 100vh;
      background-color: #34495e;
      color: #ffffff;
      padding: 15px 30px;
      transition: width 0.5s;
      box-shadow: 2px 0 5px rgba(0, 0, 0, 0.2);
    }

    #sidebar.collapsed {
      width: 80px;
    }

    #main-content {
      margin-left: 250px;
      height: 100vh;
      background-color: #f1c40f;
      color: #34495e;
      transition: margin-left 0.5s;
      padding: 80px;
    }

    #main-content.expanded {
      margin-left: 80px;
    }

    #toggle-button {
      background-color: #e74c3c;
      color: #ffffff;
      padding: 10px 20px;
      border: none;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    #toggle-button:hover {
      background-color: #c0392b;
    }
  </style>
  <body>
    <div id="sidebar">
      <button id="toggle-button">Toggle Sidebar</button>
      <p>Sidebar Content</p>
    </div>
    <div id="main-content">Main Content</div>
    <script id="solution" defer>
      document
        .getElementById("toggle-button")
        .addEventListener("click", function () {
          const sidebar = document.getElementById("sidebar");
          const mainContent = document.getElementById("main-content");
          sidebar.classList.toggle("collapsed");
          mainContent.classList.toggle("expanded");
        });
    </script>
  </body>
</html>
```
