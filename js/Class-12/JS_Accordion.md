**Raw Problem**

**Problem Description:**
Create an interactive accordion component using HTML, CSS, and JavaScript. An accordion is a vertically stacked list of items, each with a header and a content section. When a user clicks on the header, the associated content section should either collapse or expand. Your task is to implement the JavaScript functionality to make the accordion work as expected. Each accordion header is a button that, when clicked, should toggle the display of the content section. Initially, all content sections should be hidden. **NOTE:** You have to make the `accordion-content` visible using the `display: block` property and hidden using the `display: none` property.

**Hints**

1. Attach a click event listener to the parent element of the buttons to make use of event delegation.
2. Use classList.contains to check if the clicked element is an accordion button.
3. Toggle the display property of the .accordion-content element that immediately follows the clicked .accordion-button.
4. Remember that the initial state of .accordion-content should be hidden (display: none).

**Solution Approach**

1. Select the parent element of the accordion items and attach a click event listener.
2. On the event listener callback function, check if the clicked target has a class of .accordion-button.
3. Get the next sibling element, which should be the .accordion-content section.
4. Toggle the display property of this content section between none and block to show or hide the content.

**Solution**

```js
const accordion = document.querySelector(".accordion");

accordion.addEventListener("click", function (e) {
  if (e.target.classList.contains("accordion-button")) {
    const content = e.target.nextElementSibling;
    if (content.style.display === "block") {
      content.style.display = "none";
    } else {
      content.style.display = "block";
    }
  }
});
```
