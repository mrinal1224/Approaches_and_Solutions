**Raw Problem**

_Problem Description:_

Given in the HTML are cards with different data-color attributes along with some regular CSS.

Write a script in JavaScript which:

1. fetches the data-color attribute of the card by double clicking on them
2. and attaches the fetched value (a color) as a class to that card.
3. Also changes the data-color attribute to "used".

Note:
Don't make any changes to the HTML and CSS.

**Hints**
Use querySelectorAll to get an array of card elements.<
Traverse through the array and add an evenListener of 'dblclick' on each of the card.
Use getAttribute to fetch the color.
Use setAttribute to change data-color attribute to 'used'.
Access the classList and add the fetched color as a class using 'classList.add'

**Solution Approach**

First, use querySelectorAll to get an array of all the card elements.

Next, loop through the array and add an event listener of 'dblclick' to each card using addEventListener method.

Then, inside the event listener function, use getAttribute method to fetch the value of the 'data-color' attribute of the card and store it in a variable.

After that, use setAttribute method to change the value of the 'data-color' attribute to 'used'.

Finally, use classList.add method to add the fetched color as a class to the card element.

**Solution**

```javascript
// 1. Use querySelectorAll to get an array of card elements.
let cards = document.querySelectorAll(".card");

// 2. Traverse through the array and add an evenListener of 'dblclick' on each of the card.
for (let i = 0; i < cards.length; i++) {
  cards[i].addEventListener("dblclick", function (e) {
    // 3. Use getAttribute to fetch the color.
    let classTobeAttached = e.currentTarget.getAttribute("data-color");
    // 4. Use setAttribute to change data-color attribute to 'used'.
    e.currentTarget.setAttribute("data-color", "used");
    // 5. Access the classList and add the fetched color as a class using 'classList.add'
    e.currentTarget.classList.add(classTobeAttached);
  });
}
```
