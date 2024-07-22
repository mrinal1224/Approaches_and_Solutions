**Raw Problem**

Write a JavaScript program in the script.js file to:

Create all the ticket's UI, based on the data present in ticketsDB in localstorage

This question is a succession to the question, **"Kanban Q5: Automate Ticket Creation from Input"**

You have been provided the boilerplate code that handles the creation of a ticket in UI,  
you need to add new code to the area marked in the script.js file to ensure that a ticket is created for all the data present in ticketsDB.

**Hint:**  
You need to store the values in Storage Object in an array, with the help of getItem() and JSON.parse() methods.  
For each value (object) in the array, create a corresponding ticket in the UI.

You can visit the "Kanban Q5: Automate Ticket Creation from Input" question again to get better idea of the boilerplate code.  
Further, please focus on passing testcases to submit the problem successfully.

1. **Retrieve Data from Local Storage:**

   - Utilize the `localStorage.getItem` method to obtain the stored JSON string representing the tickets array.

2. **Parse JSON String into Array:**

   - Use `JSON.parse` to convert the JSON string obtained from local storage into a JavaScript array.
   - Assign the result to a variable, e.g., `ticketsArr`.

3. **Iterate Over Each Ticket Object in the Array:**

   - Utilize an array iteration method (e.g., `forEach`) to loop through each object in the `ticketsArr` array.

4. **Call `createTicket` Function for Each Ticket:**
   - Pass the relevant properties of each ticket object (e.g., `ticketTask`, `ticketColor`, `ticketID`) as arguments to the `createTicket` function.
   - Ensure that the `createTicket` function is defined elsewhere in your code to handle the creation of a ticket based on these properties.

**Solution Approach**

```javascript
// Step 1: Retrieve Data from Local Storage
let ticketsArr = JSON.parse(localStorage.getItem("ticketsDB"));

// Step 2: Parse JSON String into Array
// ticketsArr now contains an array of ticket objects

// Step 3: Iterate Over Each Ticket Object in the Array
ticketsArr.forEach(function (ticket) {
  // Step 4: Call createTicket Function for Each Ticket
  createTicket(ticket.ticketTask, ticket.ticketColor, ticket.ticketID);
});
```

Ensure that the `createTicket` function is defined elsewhere in your code and expects arguments for task, color, and ID to create a ticket based on those properties. Adjust the property names accordingly based on the actual structure of your ticket objects.

**Solution**

```javascript
let ticketsArr = JSON.parse(localStorage.getItem("ticketsDB"));

// CALLING createTicket() function for each value in ticketsArr
ticketsArr.forEach(function (ticket) {
  createTicket(ticket.ticketTask, ticket.ticketColor, ticket.ticketID);
});
```
