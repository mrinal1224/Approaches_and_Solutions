**Raw Problem**

In the HTML provided, there is a list with every item containing an individual delete button and a remove all button on top of the list.

Write a JavaScript program that performs the following tasks:

**Task 1:**  
Make all the individual delete buttons work.  
Set the list item's (`li` element) display style property as 'none'.

**Task 2:**  
Make the Remove All button work.  
Set the entire list's (`ul` element) display style property as 'none'.

**Hints**

1. Use `querySelectorAll` to get an array of individual delete buttons.
2. Traverse through the array and add an eventListener of 'click' to all the delete buttons.
3. Set the `style->display` property of the corresponding `li` element to 'none' when clicked.
4. Add an eventListener of 'click' to the Remove All button.
5. Set the `style->display` property of `ul` element to 'none' when clicked.

**Solution Approach**

1. Use `querySelectorAll` to select all the delete buttons on the page and store them in an array.
2. Loop through the array of delete buttons and add an event listener of 'click' to each one using the `addEventListener()` method.
3. Inside the event listener function, use the `this` keyword to refer to the button that was clicked. Use the `parentNode` property to access the corresponding `li` element, and set its `style->display` property to 'none' using the `style.display` property.
4. Use `querySelector` to select the 'Remove All' button on the page, and add an event listener of 'click' to it using the `addEventListener()` method.
5. Inside the event listener function for the 'Remove All' button, use `querySelector` to select the `ul` element and set its `style->display` property to 'none' using the `style.display` property.

**Solution**

```html
<script>
  // Task 1:
  let allDeleteBtns = document.querySelectorAll("li button");

  for (let i = 0; i < allDeleteBtns.length; i++) {
    allDeleteBtns[i].addEventListener("click", (e) => {
      allDeleteBtns[i].parentElement.style.display = "none";
    });
  }

  // Task 2:
  let removeAllBtn = document.getElementById("all");

  removeAllBtn.addEventListener("click", (e) => {
    document.querySelector("ul").style.display = "none";
  });
</script>
```
