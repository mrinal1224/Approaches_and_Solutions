**Raw Problem**

Write a JS program that can create a new ticket based on the input being provided.

You have been given boilerplate HTML and CSS code that you need to study and utilize.

The `.textArea-cont` in the input modal would take in the content of the ticket. Whenever the user inputs the content and presses the 'shift' key, it should:

1. Create a new ticket (`div.ticket-cont`) with the following HTML structure:

   ```html
   <div class="ticket-color ${ticketColor}"></div>
   <div class="ticket-id">#${id}</div>
   <div class="task-area">${ticketTask}</div>
   <div class="ticket-lock">
     <i class="fa-solid fa-lock"></i>
   </div>
   ```

2. Where out of the variables in the above boilerplate:

   1. `ticketColor` can be of any color.
   2. `id` should be from the `ticketID` variable, starting from 0 and incrementing for each ticket.
   3. `ticketTask` should be the text input by the user in the `.textArea-cont`.

3. You need to add this new ticket to the `div.main-cont`.

The boilerplate JS code contains a `createTicket()` function that you need to complete in order to make the feature work.

Write the code in `script.js` file.

**Hints**

1. **Function Purpose:**

   - The `createTicket` function is designed to create and add a new ticket to the main container.

2. **Ticket ID:**

   - Each ticket has a unique ID that is incremented with each new ticket created.

3. **Create Ticket Container:**

   - The function starts by creating a new `div` element, representing the container for the ticket.
   - The class "ticket-cont" is added to this container.

4. **Ticket Content:**

   - The content of the ticket container is set using `innerHTML`.
   - The content includes a color indicator, ticket ID, task area, and a ticket lock.

5. **Appending to Main Container:**

   - The created ticket container is appended to the main container, suggesting that `mainCont` is a reference to the main container where the tickets will be displayed.

6. **Dynamic Ticket Color:**

   - The color of the ticket is determined dynamically based on the `ticketColor` parameter provided when calling the function.

7. **Lock Icon:**

   - Each ticket has a lock icon (`<i class="fa-solid fa-lock"></i>`) indicating some form of lock or security feature.

8. **Task Area:**
   - The task area of the ticket displays the content of the `ticketTask` parameter provided when calling the function.

By understanding these hints, you should have a clear idea of how the `createTicket` function works and what elements and content it adds to the main container when called.

**Solution Approach**

### Step 1: Function Definition

```javascript
function createTicket(ticketTask, ticketColor) {
  // Code for the function goes here
}
```

### Step 2: Generate Unique ID

```javascript
let ticketID = 1; // Initialize a counter variable outside the function

function createTicket(ticketTask, ticketColor) {
  let id = ticketID++; // Increment the counter to get a unique ID
  // Rest of the code goes here
}
```

### Step 3: Create Ticket Container

```javascript
function createTicket(ticketTask, ticketColor) {
  let id = ticketID++;
  let ticketCont = document.createElement("div"); // Create a new div element
  ticketCont.setAttribute("class", "ticket-cont"); // Set class attribute
  // Rest of the code goes here
}
```

### Step 4: Set Ticket Content

```javascript
function createTicket(ticketTask, ticketColor) {
  let id = ticketID++;
  let ticketCont = document.createElement("div");
  ticketCont.setAttribute("class", "ticket-cont");

  ticketCont.innerHTML = `<div class="ticket-color ${ticketColor}"></div>
    <div class="ticket-id">#${id}</div>
    <div class="task-area">${ticketTask}</div>
    <div class="ticket-lock">
      <i class="fa-solid fa-lock"></i>
    </div>`;
  // Rest of the code goes here
}
```

### Step 5: Append to Main Container

Assuming `mainCont` is a reference to the main container:

```javascript
function createTicket(ticketTask, ticketColor) {
  let id = ticketID++;
  let ticketCont = document.createElement("div");
  ticketCont.setAttribute("class", "ticket-cont");

  ticketCont.innerHTML = `<div class="ticket-color ${ticketColor}"></div>
    <div class="ticket-id">#${id}</div>
    <div class="task-area">${ticketTask}</div>
    <div class="ticket-lock">
      <i class="fa-solid fa-lock"></i>
    </div>`;

  mainCont.append(ticketCont); // Append the ticket container to the main container
}
```

### Step 6: Dynamic Ticket Color

```javascript
function createTicket(ticketTask, ticketColor) {
  let id = ticketID++;
  let ticketCont = document.createElement("div");
  ticketCont.setAttribute("class", "ticket-cont");

  ticketCont.innerHTML = `<div class="ticket-color ${ticketColor}"></div>
    <div class="ticket-id">#${id}</div>
    <div class="task-area">${ticketTask}</div>
    <div class="ticket-lock">
      <i class="fa-solid fa-lock"></i>
    </div>`;

  mainCont.append(ticketCont);
}
```

### Step 7: Final Code

```javascript
let ticketID = 1; // Initialize a counter variable outside the function
let mainCont = document.querySelector(".main-cont"); // Assuming mainCont is a reference to the main container

function createTicket(ticketTask, ticketColor) {
  let id = ticketID++;
  let ticketCont = document.createElement("div");
  ticketCont.setAttribute("class", "ticket-cont");

  ticketCont.innerHTML = `<div class="ticket-color ${ticketColor}"></div>
    <div class="ticket-id">#${id}</div>
    <div class="task-area">${ticketTask}</div>
    <div class="ticket-lock">
      <i class="fa-solid fa-lock"></i>
    </div>`;

  mainCont.append(ticketCont);
}
```

This provides a complete `createTicket` function that creates a new ticket with unique features and appends it to the main container.

**Solution**

```javascript
function createTicket(ticketTask, ticketColor) {
  let id = ticketID++;
  let ticketCont = document.createElement("div");
  ticketCont.setAttribute("class", "ticket-cont");

  ticketCont.innerHTML = `<div class="ticket-color ${ticketColor}"></div>
     <div class="ticket-id">#${id}</div>
     <div class="task-area">${ticketTask}</div>
     <div class="ticket-lock">
       <i class="fa-solid fa-lock"></i>
    </div>`;

  mainCont.append(ticketCont);
}
```
