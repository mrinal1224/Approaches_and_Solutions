**Raw Problem**

Write a script using JavaScript to make the filter work.

The filter has 4 categories: none, Action, Romance, Comedy.

Each movie card is a `div` with an `h3` and `p` element. The `p` element has a `data-category` attribute that holds the information about the category of the movie.

Use the value of this `data-category` attribute to filter the movies based on the selected category from the drop-down menu.

**NOTE:**  
If the category is selected as 'none', show all the movies.  
To hide a movie card, change the `style->display` property of the `div` to 'none'.  
To show a movie card, change the `style->display` property of the `div` to 'block'.

**Hints**

- Add an eventListener of 'change' to the select element to access the filter category.
- Use `querySelectorAll` to get access to an array of all the `p` elements.
- Traverse through the array of `p` elements and based on the value of the selected category, set the `style->display` property of the `parentElement`.

**Solution Approach:**

1. Use `querySelector` to select the select element that you want to add the event listener to.
2. Add an event listener of 'change' to the select element using `addEventListener` method.
3. Inside the 'change' event listener function, use the `value` property of the select element to get the selected category.
4. Use `querySelectorAll` to get an array of all the `p` elements that you want to filter.
5. Loop through the array of `p` elements and, for each element, check if the value of its `data-category` attribute matches the selected category. If it does, set the `style.display` property of its `parentElement` to 'block'. Otherwise, set it to 'none'.

**Solution**

```html
<!-- Complete Solution : -->
<script>
  let filter = document.querySelector("select");

  filter.addEventListener("change", function () {
    let filterValue = filter.value;

    let allTickets = document.querySelectorAll("p");

    if (filterValue === "none") {
      for (let i = 0; i < allTickets.length; i++) {
        allTickets[i].parentElement.style.display = "block";
      }
    } else {
      for (let i = 0; i < allTickets.length; i++) {
        if (allTickets[i].getAttribute("data-category") != filterValue) {
          allTickets[i].parentElement.style.display = "none";
        } else {
          allTickets[i].parentElement.style.display = "block";
        }
      }
    }
  });
</script>
```
