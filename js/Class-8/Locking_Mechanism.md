**Raw Problem**

**Problem Description:**
Write a JavaScript program in the `<script>` tag to:

Implement the **locking mechanism feature** for all the tickets present.
![locking-mechanism-gif](https://raw.githubusercontent.com/pantchayan/scaler-images/master/Kanban/locking-mechanism-gif.gif)

The feature works under two different states of **locked and unlocked**.

**State 1.** When the ticket is locked and clicked:

1. locked button changes to unlocked button.
2. task-area is set to editable.

**State 2.** When the ticket is unlocked and clicked:

1. unlocked button changes to locked button.
2. task-area is set to uneditable.

**Important information and algorithms:**

**1. How to change the buttons, editability of tasks and keep an account of the state?**
You are provided a single button inside the div.ticket-lock,
and the structure of the ticket is as follows:

```html
<div class="ticket-color ${ticketColor}"></div>
<div class="ticket-id">${id}</div>
<div class="task-area">${ticketTask}</div>
<div class="ticket-lock">
  <button>Locked</button>
</div>
```

Based on these, below is the algorithm to be followed.

**Algorithm:**
You can to utilise the class (will be ticket-lock or ticket-unlock) of the parent div of button to find the current state, if its state 1 (locked) or state 2 (unlocked).
Then whenever the button is clicked:
In state 1, you need to:

1. change the class of 'ticket-lock' to 'ticket-unlock'
2. change the innerText of button from 'Locked' to 'Unlocked'
3. set the contenteditable attribute of task-area to true

In state 2, you need to:

1. change the class of 'ticket-unlock' to 'ticket-lock'
2. change the innerText of button from 'Unlocked' to 'Locked'
3. set the contenteditable attribute of task-area to false

After performing the above steps, it is also important to update the global ticketArr array with the new ticketTask.

Further, please focus on passing test cases to submit the problem successfully.

**Hints**

1. Use document.querySelectorAll('.ticket-cont') to get access to all the tickets in the document and store them in an array.
2. Traverse this array and add a 'click' eventListener to the button of each of the ticket container element in the array.
3. Get access to the: button's parent div, button and ticket's task-are using relevant selectors
4. Utilise the class of the parent div of button to find the current state
5. Use conditional statements (if-else) to write the algorithm based on states, which is mentioned in the description.

**Solution Approach**

To achieve the tasks mentioned in the description, you can follow the steps outlined below.
Firstly, use document.querySelectorAll('.ticket-cont') to access all the ticket containers in the document, and store them in an array.

Next, traverse through this array using a loop, and add a 'click' eventListener to the icon (img element) of each of the ticket container elements in the array.

In the callback function for this eventListener, you can get access to the icon's parent div, icon's image and the ticket's task area using relevant selectors. This can be done using methods such as querySelector() and parentElement.

After that, you can utilize the class of the parent div of the icon to find the current state of the ticket. This can be done using methods such as classList.contains().

Finally, use conditional statements (if-else) to write the algorithm based on the current state of the ticket. This will enable you to update the state of the ticket based on the user's interaction with the icon.

By following these steps, you can ensure that your code will add an eventListener to the icon of each ticket, and will respond accordingly based on the current state of the ticket. This will allow you to implement the required functionality and update the state of the ticket based on the user's interaction with the icon.

**Complete Solution**

```html
<script>
  // FETCHING ALL THE TICKET CONTAINERS IN AN ARRAY
  let ticketContArr = document.querySelectorAll(".ticket-cont");

  // TRAVERSING THROUGH THAT ARRAY
  for (let i = 0; i < ticketContArr.length; i++) {
    // ADDING CLICK EVENT LISTENER TO THE BUTTON
    ticketContArr[i].querySelector("button").addEventListener("click", (e) => {
      let ticket = ticketContArr[i];
      let ticketTaskArea = ticket.querySelector(".task-area");
      let buttonDiv = ticketContArr[i].children[3];
      let button = buttonDiv.querySelector("button");

      // CHANGING THE ICON, CLASS AND SETTING TEXT AREA AS EDITABLE
      if (buttonDiv.classList.contains("ticket-lock")) {
        button.innerText = "Unlocked";
        buttonDiv.classList.remove("ticket-lock");
        buttonDiv.classList.add("ticket-unlock");
        ticketTaskArea.setAttribute("contenteditable", "true");
      } else {
        button.innerText = "Locked";
        buttonDiv.classList.remove("ticket-unlock");
        buttonDiv.classList.add("ticket-lock");
        ticketTaskArea.setAttribute("contenteditable", "false");
      }

      // UPDATING MAIN TICKET ARRAY
      let id = ticket.querySelector(".ticket-id").innerText;
      let ticketIdx = getTicketIdx(id);
      ticketsArr[ticketIdx].ticketTask = ticketTaskArea.innerText;
    });
  }

  function getTicketIdx(id) {
    let ticketIdx = ticketsArr.findIndex(function (ticketObj) {
      return ticketObj.ticketID === id;
    });

    return ticketIdx;
  }
</script>
```
