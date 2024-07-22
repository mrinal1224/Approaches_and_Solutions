**Raw Problem**

You need to write JS program to  
Create a Storage Object names 'ticketsDB' in Browser's localstorage.  
The localStorage read-only property of the window interface allows you to access a Storage object for the Document's origin; the stored data is saved across browser sessions.
The following snippet accesses the current domain's local Storage object and adds a data item to it using Storage.setItem()

```
localStorage.setItem("myCat", "Tom");
```

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

**Solution**

```js
localStorage.setItem("ticketsDB", JSON.stringify(ticketsArr));
```
