**Raw Problem**

Write a JavaScript program in the script.js file to:

To update the ticketsArr and ticketsDB Storage Object in the localstorage.

This question is a succession to the question, **"Kanban Q8: Button to Delete Ticket from UI"**

You have been provided the boilerplate code that handles the deletion of the ticket from UI,  
you need to add new code to the area marked in the script.js file to ensure the task to update ticketsDB in localstorage.

**Hint:**  
You need to write a function first to get the index of the ticket being deleted by matching the ids,  
then use this index to delete the item from the ticketArr and then update the ticketsDB with the updated array after stringifying it.

You can visit the "Kanban Q8: Button to Delete Ticket from UI" question again to get better idea of the boilerplate code.  
Further, please focus on passing testcases to submit the problem successfully.

Here are step-by-step hints for the solution code:

1. **Retrieve Ticket ID from HTML Element:**

   - Use `ticketContArr[i].querySelector(".ticket-id").innerText` to get the text content of the element with class `.ticket-id` within the `ticketContArr[i]` element.

2. **Get the Index of the Ticket in the Array:**

   - Call the `getTicketIdx` function with the retrieved ticket ID as an argument.
   - This function uses `findIndex` to locate the index of the ticket in the `ticketsArr` array based on its ID.

3. **Remove the Ticket from the Array:**

   - Use the `splice` method on `ticketsArr` to remove the ticket at the index obtained from the previous step.
   - The `splice` method modifies the array in place.

4. **Update Local Storage with Modified Array:**
   - Convert the modified `ticketsArr` array to a JSON string using `JSON.stringify`.
   - Use `localStorage.setItem` to update the "ticketsDB" item in the local storage with the updated JSON string.

The `getTicketIdx` function plays a crucial role in finding the index of the ticket based on its ID, allowing for efficient removal from the array.

**Solution Approach**

```js
// Step 1: Retrieve Ticket ID from HTML Element
let ticketID = ticketContArr[i].querySelector(".ticket-id").innerText;

// Step 2: Get the Index of the Ticket in the Array
let idx = getTicketIdx(ticketID);

// Step 3: Remove the Ticket from the Array
ticketsArr.splice(idx, 1);

// Step 4: Update Local Storage with Modified Array
localStorage.setItem("ticketsDB", JSON.stringify(ticketsArr));

// Step 5: Define the getTicketIdx function
function getTicketIdx(id) {
  // Step 6: Use findIndex to locate the index of the ticket in the ticketsArr array
  let ticketIdx = ticketsArr.findIndex(function (ticketObj) {
    return ticketObj.ticketID === id;
  });

  // Step 7: Return the index of the ticket
  return ticketIdx;
}
```

**Solution**

```js
// FETCHING ALL THE TICKET CONTAINERS IN AN ARRAY
let ticketContArr = document.querySelectorAll(".ticket-cont");
let removeBtn = document.querySelector(".remove-btn");

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
  ticketContArr[i].addEventListener("click", (e) => {
    if (!removeFlag) return;

    ticketContArr[i].remove(); // ui Removal

    // WRITE SOLUTION HERE ============================================
    let idx = getTicketIdx(
      ticketContArr[i].querySelector(".ticket-id").innerText
    );

    ticketsArr.splice(idx, 1);
    localStorage.setItem("ticketsDB", JSON.stringify(ticketsArr));
  });
}

// A FUNCTION TO GET THE TICKET INDEX FROM MAIN DATA ARRAY
function getTicketIdx(id) {
  let ticketIdx = ticketsArr.findIndex(function (ticketObj) {
    return ticketObj.ticketID === id;
  });

  return ticketIdx;
}
```
