**Raw Problem**

You need to write JS program, so that

When the ticket color band (div.ticket-color) is clicked:

1. It changes the color.
2. The new color should be picked from 'colors' Array.
3. The new color should be the next color mentioned in the 'colors' Array.
   1.For example:

   2. let colors = ["lightpink", "lightgreen", "lightblue", "black"];

   3. According to the colors array if the color of the ticket-band is 'lightpink',
   4. Then after clicking on it, the new color should be 'lightgreen'

4. To change the color you just need to add the color name as a class to the div.ticket-color element.
5. Make sure to remove the previous color class from the element.

For example:

<div class="ticket-color lightpink"></div>  
  
after clicking, should become:  
  
<div class="ticket-color lightgreen"></div>  
  
Write the code in the script.js file, you have been provided some boilerplate code to help.

**Hints**

1. **Select the Ticket Color Band Element:**

   - Use `querySelector` to select the element with the class `.ticket-color` within the given `ticket`.

2. **Add Event Listener for Click Event:**

   - Use `addEventListener` to attach a click event listener to the `ticketColorBand` element.

3. **Retrieve Current Ticket Color:**

   - Get the current color applied to the `ticketColorBand` element. This is typically stored as a class on the element.

4. **Find the Index of Current Color in the Colors Array:**

   - Use `findIndex` on the `colors` array to find the index of the current color.

5. **Increment the Current Color Index:**

   - Increment the index found in the previous step.

6. **Calculate the New Color Index with Modulo:**

   - Use the modulo operator (`%`) to ensure the index wraps around when it exceeds the length of the `colors` array.

7. **Retrieve the New Ticket Color:**

   - Get the new color from the `colors` array using the calculated index.

8. **Remove the Current Color Class and Add the New Color Class:**
   - Use `classList.remove` to remove the current color class, and `classList.add` to add the new color class to the `ticketColorBand` element.

By following these steps, the `handleColor` function should successfully handle the click event on the ticket color band, cycle through the colors, and update the color of the ticket accordingly.

**Solution Approach**

```javascript
function handleColor(ticket) {
  // Step 1: Select the Ticket Color Band Element
  let ticketColorBand = ticket.querySelector(".ticket-color");

  // Step 2: Add Event Listener for Click Event
  ticketColorBand.addEventListener("click", function () {
    // Step 3: Retrieve Current Ticket Color
    let currentTicketColor = ticketColorBand.classList[1];

    // Step 4: Find the Index of Current Color in the Colors Array
    let currentColorIdx = colors.findIndex(function (color) {
      return currentTicketColor === color;
    });

    // Step 5: Increment the Current Color Index
    currentColorIdx++;

    // Step 6: Calculate the New Color Index with Modulo
    let newTicketColorIdx = currentColorIdx % colors.length;

    // Step 7: Retrieve the New Ticket Color
    let newTicketColor = colors[newTicketColorIdx];

    // Step 8: Remove the Current Color Class and Add the New Color Class
    ticketColorBand.classList.remove(currentTicketColor);
    ticketColorBand.classList.add(newTicketColor);
  });
}
```

This code assumes that the `colors` array is defined somewhere in your code, containing the possible colors for the tickets. The `handleColor` function is designed to be applied to a ticket element, and when the color band within that ticket is clicked, it cycles through the colors defined in the `colors` array.

**Solution**

```javascript
let ticket = document.querySelector(".ticket-cont");

let colors = ["lightpink", "lightgreen", "lightblue", "black"];

handleColor(ticket);

function handleColor(ticket) {
  let ticketColorBand = ticket.querySelector(".ticket-color");

  ticketColorBand.addEventListener("click", function () {
    let currentTicketColor = ticketColorBand.classList[1];

    let currentColorIdx = colors.findIndex(function (color) {
      return currentTicketColor === color;
    });

    currentColorIdx++;

    let newTicketColorIdx = currentColorIdx % colors.length;

    let newTicketColor = colors[newTicketColorIdx];

    ticketColorBand.classList.remove(currentTicketColor);
    ticketColorBand.classList.add(newTicketColor);
  });
}
```
