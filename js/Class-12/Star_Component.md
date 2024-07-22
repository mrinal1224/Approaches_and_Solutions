**Raw Problem**

**Problem Description:**

Write a JS program to make the **star rating component** work.

![star-gif](https://i.postimg.cc/GtWs1h4n/star-gif.gif)

Read the entire problem description carefully to understand the necessary details.

The HTML code that is provided holds the following components and functions:  
1\. **div#star-container** => Containing 5 span.star inside it.  
2\. **span.star** => Individual star symbol with default grey color.  
3\. **span#count** => Containing the Rating Count, set as default number of '0'

**You have to a JS program such that:**  
1\. Whenever mouse hovers over any span.star:

1.1. All the stars till the target span.star, change color to yellow.

1.2. To do this you need to add class of 'star-filled' to stars that need to be yellow.

1.3. and remove the class of 'star-filled' from all the stars that need to be of default color. (grey)

2\. Whenever any span.star is clicked on:

2.1. You need to repeat step 1 to color the stars yellow till the target span.star

2.2. Update the Rating Count (span#count) with the star points. (Ex: If third star is clicked, rating count becomes 3)

2.3. Store the value of star points globally, to update the colors when the mouse hovers over or leaves any span.star

3\. Whenever mouse leaves any span.star after hover:

3.1. Remove the class of 'star-filled' from all the stars beyond the selected star points global value. (set to 0 by default)

You can refer to the HTML code to understand the specificity of the selectors.  
**Please don't make any changes to the HTML and CSS code and structure.**

Use the above information to write the entire JS program in the script.js file or script tag.  
**Refer to the test cases** to further understand the criteria to submit the problem successfully.

Feel free to access hints to get help/assistance.

**Hints**

1. Add eventListener of 'mouseover', 'click', and 'mouseleave' on the div#star-container to write the program.

2. You can utilise Event.target.dataset.index to find the index of the star that being hovered over or clicked on.
3. Keep a global star count variable, and loop through all the span.star based on that to either add class of 'star-filled' or remove it.

4. You can loop twice, first to remove the class of 'star-filled' from all the span.star and then loop to add class of 'star-filled' till the star point value.

**Solution Approach**
To create an interactive star rating system, you need to add event listeners to the star container div. You can use the "mouseover", "click", and "mouseleave" events to create a responsive user interface. To find the index of the star that is being hovered over or clicked on, you can use the "Event.target.dataset.index" property. The program should keep track of the number of filled stars using a global variable. You can loop through all the star elements and either add or remove the "star-filled" class based on the current number of filled stars. To achieve this, you can loop twice, first to remove the class of "star-filled" from all the star elements and then loop again to add the class of "star-filled" to the appropriate number of star elements. Finally, update the star count display using the "innerText" property. When the mouse leaves the star container div, you should restore the number of filled stars to its previous value by looping through the star elements and adding the "star-filled" class up to the previous number of filled stars.

**Solution**

```js
let container = document.getElementById("star-container");
let star = document.querySelectorAll(".star");
let filled = 0;

container.addEventListener("click", function (e) {
let currClicked = e.target.dataset.index;

for (let i = 0; i < 5; i++) {
star\[i\].classList.remove("star-filled");
}

for (let i = 0; i < currClicked; i++) {
star\[i\].classList.add("star-filled");
}

document.getElementById("count").innerText =`${currClicked}`;

filled = currClicked;
});

container.addEventListener("mouseover", function (e) {
let currHovered = e.target.dataset.index;

for (let i = 0; i < 5; i++) {
star[i].classList.remove("star-filled");
}

for (let i = 0; i < currHovered; i++) {
star[i].classList.add("star-filled");
}
});

container.addEventListener("mouseleave", function (e) {
for (let i = 0; i < 5; i++) {
star[i].classList.remove("star-filled");
}

for (let i = 0; i < filled; i++) {
star[i].classList.add("star-filled");
}
});
```
