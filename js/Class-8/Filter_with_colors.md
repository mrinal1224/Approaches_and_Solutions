**Raw Problem**

**Write a JavaScript program to:**
Implement the filter feature for the tickets based on the priority colors. (lightpink, lightgreen, lightblue, black)

![color-filter-gif](https://raw.githubusercontent.com/pantchayan/scaler-images/master/Kanban/color-filter-gif.gif)

**Task 1:**
Whenever a particular color is clicked from the toolbox =>

1. Remove all the existing tickets from Document.
2. Only the tickets with the assigned priority colors should be added to the Document.

**Task 2:**
Whenever any of the color is double clicked =>

1. Remove all the existing tickets from Document.
2. All the tickets (regardless of color) should be added to the Document.

**Important information and algorithms:**

**1. How to add a ticket to the document?**
createTicket(ticket-task, ticket-color, ticket-id) function has been provided in the script.js,
this function creates and adds a ticket to the Document with below structure.

Ticket structure :

```html
<div class="ticket-cont">
  <div class="ticket-color"></div>
  <div class="ticket-id">id 1</div>
  <div class="task-area">this is task 1</div>
  <div class="ticket-lock">
    <i class="fa-solid fa-lock"></i>
  </div>
</div>
```

**2. How to access the ticket information (ticket-task, ticket-color, ticket-id)?**
To create the tickets, you would utilise createTicket(ticket-task, ticket-color, ticket-id) function,
this function requires several parameters as input.
To access these ticket values, you are provided a global variable ticketsArr
which is an Array of Objects holding objects containing individual values (ticketTask, ticketColor, ticketID) of 4 tickets.

**3. How to remove all the tickets from the document?**
To remove unwanted tickets from the Document, utilise DOM function Element.remove()
To select a ticket element to, use class 'ticket-cont', as descibed on the ticket structure above.

Below are the algorithms that need to be followed for both the tasks,

**Algorithm for Task 1:**
Step 1. After removing every ticket from the Document.
Step 2. You can access 'ticketsArr' array,
Step 3. filter it on the basis of the selected color from the toolBox (**don't overwrite global array 'ticketsArr'**)
Step 4. and create individual tickets for the filtered ticket objects.

**Algorithm for Task 2:**
Step 1. After removing every ticket from the Document.
Step 2. You can access 'ticketsArr' array,
Step 3. and create individual tickets for all the ticket objects.

Further, please focus on passing testcases to submit the problem successfully.

**Hints**

1. Access the toolBox color boxes array using querySelectorAll with '.color' selector.
2. Traverse on this array and add an Element.addEventListener('click') on each of the box.
3. In the callback function for this eventListener of 'click', code the algorithm for Task 1 mentioned in the problem description.
4. Again, while traversing the array, add an Element.addEventListener

**Solution Approach**

To accomplish the tasks mentioned in the problem description, you can follow the steps below.

First, access the color boxes array using the querySelectorAll method with the '.color' selector. This will give you an array of all the color boxes on the page.

Next, traverse through this array using a loop, and add an EventListener with the 'click' event to each of the boxes. In the callback function for this EventListener, write the algorithm for Task 1.

After that, while traversing through the same array, add another EventListener

By following these steps, you can ensure that your code will respond to both single-click and double-click events on the color boxes, and that it will execute the appropriate algorithms for Task 1 and Task 2, respectively.

**Complete Solution**

```javascript
let toolBoxColors = document.querySelectorAll(".color");
// TOOL BOX - COLOR FILTERS
for (let i = 0; i < toolBoxColors.length; i++) {
  toolBoxColors[i].addEventListener("click", function () {
    let selectedToolBoxColor = toolBoxColors[i].classList[0];

    let filteredTickets = ticketsArr.filter(function (ticketObj) {
      return selectedToolBoxColor === ticketObj.ticketColor;
    });

    let allTickets = document.querySelectorAll(".ticket-cont");

    for (let i = 0; i < allTickets.length; i++) {
      allTickets[i].remove();
    }

    filteredTickets.forEach(function (filteredObj) {
      createTicket(
        filteredObj.ticketTask,
        filteredObj.ticketColor,
        filteredObj.ticketID
      );
    });
  });

  toolBoxColors[i].addEventListener("dblclick", function () {
    let allTickets = document.querySelectorAll(".ticket-cont");

    for (let i = 0; i < allTickets.length; i++) {
      allTickets[i].remove();
    }

    ticketsArr.forEach(function (ticketObj) {
      createTicket(
        ticketObj.ticketTask,
        ticketObj.ticketColor,
        ticketObj.ticketID
      );
    });
  });
}
```
