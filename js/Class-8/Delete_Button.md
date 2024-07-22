**Raw Problem**

**Problem Description:**
Write a JavaScript program in the `<script>` tag to:

Implement the **delete feature** for all the tickets present.
![delete-button-gif](https://raw.githubusercontent.com/pantchayan/scaler-images/master/Kanban/delete-button.gif)

The feature should work as follows:

1. When the Delete Button (div.remove-btn), which is a cross button in the tool bar, is clicked:
   1. It gives an alert that the 'delete button has been activated'
   2. This means that now if any ticket is clicked, it gets removed from the UI (User Interface)
   3. The background color of the div with class 'remove-btn' turns 'red' when the delete button is activated.
2. When the Delete Button is clicked again:
   1. It deactivates the delete button
   2. This means now clicking on a ticket would no longer remove it from the UI.
   3. The background color of the div with class 'remove-btn' turns back to inherited bgcolor from parent.

**Important information and algorithms:**

**1. How to keep an account of states associated with delete button?**

The delete button is in the following structure:

<div class="action-btn-cont">
   <div class="remove-btn">
      <img src="cross-logo.png" alt="cross-logo" height="50%">
   </div>
</div>

Here, div.action-btn-cont is the toolbox containing div.remove-btn with an image of cross inscribed in it.
So when the the div.remove-btn is clicked, it should make the delete feature work.

To know whether the delete button is activated or not, you can utlise a global boolean variable working as a Flag.

**Algorithm 1 to set states:**
Whenever delete button is clicked:
If the Flag says the delete button was inactive:

1. negate the Flag value.
2. create an Alert that says 'delete button has been activated'
3. set the background color of div.remove-btn to 'red'

If the Flag says the delete button was active:

1. negate the Flag value.
2. set the background color of div.remove-btn to 'inherit'

**2. How to remove a ticket from the UI?**

**Algorithm 2 to remove a ticket:**
For each of the ticket, add an eventListener of 'click' such that whenever a ticket is clicked,
it checks the Flag value determing the activation state of the delete button.
If the Flag says the delete button is inactive:

1. Don't do anything and return back.

If the Flag says the delete button is active:

1. Use the Element.remove() function to remove the ticket from the UI.

As a bonus:
After performing the above steps, you can try to update the global ticketArr array by removing the ticket data from it as well.

Further, please **focus on passing test cases** to submit the problem successfully.

**Hints**

1. Both the Algorithms, 1 and 2 from the problem description need to be implemented seperately.

2. Algorithm 1 should be followed in the callback function for the 'click' eventListener on the div.remove-btn (delete button).

3. Use document.querySelectorAll('.ticket-cont') to get access to all the tickets in the document and store them in an array.

4. Traverse this array and add a 'click' eventListener to the ticket that handles Algorithm 2 from the description.

**Solution Approach**
To implement the two algorithms described in the problem, there are a few steps that need to be followed. Firstly, both algorithms need to be implemented separately. This means creating two separate functions, each with their own set of instructions to execute.

Next, Algorithm 1 should be followed in the callback function for the 'click' eventListener on the div.remove-btn (delete button). This means that when the user clicks on the delete button, the function that implements Algorithm 1 should be triggered. This function should remove the corresponding ticket from the page.

To get access to all the tickets in the document, we can use the document.querySelectorAll('.ticket-cont') method. This will return a list of all the ticket containers on the page, which can be stored in an array.

Once we have the array of ticket containers, we can traverse it using a loop and add a 'click' eventListener to each ticket. This eventListener should trigger the function that implements Algorithm 2 from the problem description. This function should toggle the expanded state of the ticket.

By following these steps, we can successfully implement both algorithms and create a fully functioning ticket deleting system on our web page.

**Complete Solution**

```html
<script>
  // Write your solution here =====================================================

  // FETCHING ALL THE TICKET CONTAINERS IN AN ARRAY
  let ticketContArr = document.querySelectorAll('.ticket-cont');
  let removeBtn = document.querySelector('.remove-btn');

  let removeFlag = false;

  // REMOVE BUTTON HANDLES removeFlag and creates ALERT
  removeBtn.addEventListener("click", function () {
  removeFlag = !removeFlag;

  if (removeFlag === true) {
  alert("delete button has been activated");
  removeBtn.style.backgroundColor = "red";
  } else {
  removeBtn.style.backgroundColor = "inherit";
  }
  });


  // TRAVERSING THROUGH THAT ARRAY
  for (let i = 0; i < ticketContArr.length; i++) {
  // ADDING CLICK EVENTLISTENER TO THE ICON
  ticketContArr\[i\].addEventListener('click', (e) => {
  if (!removeFlag) return;

  let idx = getTicketIdx(ticketContArr\[i\].querySelector('.ticket-id').innerText);

  let deletedElement = ticketsArr.splice(idx, 1);

  console.log(deletedElement)

  ticketContArr\[i\].remove(); // ui Removal

  })
  }

  // A FUNCTION TO GET THE TICKET INDEX FROM MAIN DATA ARRAY
  function getTicketIdx(id) {
  let ticketIdx = ticketsArr.findIndex(function (ticketObj) {
  return ticketObj.ticketID === id;
  })

  return ticketIdx;
  }
</script>
```
