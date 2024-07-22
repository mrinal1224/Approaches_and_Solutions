**Raw Problem**<br />

 <div id=raw_problem_description_markdown_content_value style="background-color: #f9f9f9; padding: 5px 10px; ">Write a single click event handler that helps to delete any list item when clicked on it, attach that handler to above list<br /><br />The HTML has majorly 3 components in following hierarchy: <br />ul &gt; li &gt; a<br /><br />Here,<br /><br />1. ul#listToDestroy:
<div style="padding-left: 30px;">1.1. contains the entire list</div>
<div style="padding-left: 30px;">1.2. has 5 li tags with unique id.</div>
<br />2. li:
<div style="padding-left: 30px;">2.1. contains an anchor tag &lt;a&gt; in it.</div>
<br />3. a:
<div style="padding-left: 30px;">3.1. contains unique innerText in it.</div>
<br /><br />Your task is to:<br />1. Whenevr clicked the specific list item, &lt;li&gt; element, from the list ul#listToDestroy.<br />2. The new list should have list items 1 less than the previous state.<br />3. Unique ID and innerText should remain intact for each list item.</div><br /><br />

**Hints**
Here are some hints to help you write the click event handler for deleting list items without providing the full code:

1. **Select the Parent Element**: You can start by selecting the parent element (the `<ul>` with id "listToDestroy") to attach the click event listener.

2. **Event Delegation**: Utilize event delegation to handle click events on the list items (`<li>`) and their child anchor tags (`<a>`). This way, you can handle clicks on any list item.

3. **Identify the Clicked Item**: Inside the event handler, identify the specific list item that was clicked. You can do this by inspecting the `e.target` property.

4. **Remove the Clicked Item**: Once you've identified the clicked list item, remove it from the parent element to achieve the desired functionality.

5. **Ensure Data Integrity**: Make sure that the unique ID and innerText of the remaining list items remain intact after the deletion.

By following these hints and using the provided solution as a reference, you should be able to create a click event handler that deletes list items when clicked while preserving the unique IDs and innerText of the remaining items.

**Solution Approach**
Here's a step-by-step approach with code for creating a click event handler to delete list items:

1. **Select the Parent Element and Attach Event Listener**:
   - Select the parent `<ul>` element with the id "listToDestroy."
   - Attach a click event listener to this parent element.

```javascript
const listToDestroy = document.getElementById("listToDestroy");
listToDestroy.addEventListener("click", function (e) {
  // Your code for the following steps goes here
});
```

2. **Identify the Clicked List Item**:
   - Inside the event handler, check if the clicked element (`e.target`) is an `<li>` element.

```javascript
if (e.target.tagName === "LI") {
  // Your code for the following steps goes here
}
```

3. **Remove the Clicked List Item**:
   - If the clicked element is an `<li>` element, you can remove it from the list by using the `remove()` method.

```javascript
if (e.target.tagName === "LI") {
  e.target.remove();
}
```

4. **Preserve Data Integrity**:
   - Ensure that the unique ID and innerText of the remaining list items are not affected by the removal of the clicked item.

By following this step-by-step approach, you can create a click event handler that deletes list items when they are clicked on while preserving the unique IDs and innerText of the remaining list items.

**Solution**

```javascript
document
  .querySelector("#listToDestroy")
  .addEventListener("click", function (e) {
    let elm = e.target.parentNode;
    elm.parentNode.removeChild(elm);
  });
```
