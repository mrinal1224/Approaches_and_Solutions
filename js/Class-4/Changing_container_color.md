**Raw Problem**  
**Write a program in JavaScript to perform the below-mentioned task:**

Use a single event handler (only one element should have an event handler attached to it) and do the following:  
By clicking the color name, change the background color of the div.container to the same.

**Note:**  
The colors are red, blue, and green.  
Don't make any changes to the boilerplate code.

**Hints**
Event delegation using a click event on ".container".  
Changing background based on clicked element's class.  
Modify the container's background using clicked element.

**Solution Approach**
The code selects an HTML element with the class "container" and assigns it to the variable container.

It adds a click event listener to the container element.

When a click event occurs within the container, the event listener function is triggered.

Inside the event listener function, `e.currentTarget` refers to the element with the "container" class, and `e.target` refers to the specific element that was clicked inside the container.

The event listener function then accesses the clicked element's class using `e.target.classList[0]` and sets the background color of the container (`e.currentTarget`) to the class name of the clicked element.

**Solution**

```js
let container = document.querySelector(".container");
container.addEventListener("click", function (e) {
  e.currentTarget.style.background = e.target.classList[0];
});
```
