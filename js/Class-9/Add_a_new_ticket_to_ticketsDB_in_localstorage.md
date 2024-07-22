**Raw Problem**

You need to write JS program to  
Add a new ticekt to Storage Object of name 'ticketsDB' in Browser's localstorage.

```
_The localStorage read-only property of the window interface allows you to access a Storage object for the Document's origin; the stored data is saved across browser sessions._
```

The following snippet accesses the current domain's local Storage object and adds a data item to it using Storage.setItem().

```
_localStorage.setItem("myCat", "Tom");_
```

You are provided with boilerplate code to add a new ticket in the UI from Input in script.js file.  
Inside the exisiting code you need to write your code solution. Marking has been done of the same as a hint.

You need to make sure that whenever the Input is made in the modal,

1. ticketsArr is updated with the new ticket information. { ticketTask, ticketColor, ticketID: id }
2. And then ticketsArr is used as a value and Storage Object ticketsDB is updated with it.

You need to use stringify the Array of Objects 'ticketsArr' provided to you in script.js file  
You can use JSON.stringify() method to acheive this.

**Hints**
The following snippet accesses the current domain's local Storage object and adds a data item to it using Storage.setItem().

```
localStorage.setItem("myCat", "Tom");
```

**Solution Approach**
The following snippet accesses the current domain's local Storage object and adds a data item to it using Storage.setItem().

```
localStorage.setItem("myCat", "Tom");
```

Using the above syntax we can devise the solution

```
  ticketsArr.push({ ticketTask, ticketColor, ticketID: id });
  localStorage.setItem("ticketsDB", JSON.stringify(ticketsArr));
```

**Solution**
The following snippet accesses the current domain's local Storage object and adds a data item to it using Storage.setItem().

```
localStorage.setItem("myCat", "Tom");
```

Using the above syntax we can devise the solution

```
  ticketsArr.push({ ticketTask, ticketColor, ticketID: id });
  localStorage.setItem("ticketsDB", JSON.stringify(ticketsArr));
```
