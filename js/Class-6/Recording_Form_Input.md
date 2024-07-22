**Raw Problem**

Write a script which takes the entry from the form and adds it into the table

The HTML has majorly 2 components:

1. **table**:

   - contains the entire table
   - has `thead` and `tbody` as immediate children
   - has a total of 3 `tr`, 1 in `thead` and 2 in `tbody`
   - each `tr` in `tbody`

2. **form**:
   - contains three input tags of type:
     - `text` for name,
     - `number` for marks,
     - `submit` for button.

Your task is to:

1. Add a new `<tr>` element inside `<tbody>` whenever the form is filled and the submit button is clicked.
2. The new `<tr>` element should have 3 `<td>` elements for SNO., Name, and Marks.
3. Name and Marks are to be retrieved from user input in the form and the SNO. is to be increased by 1 at every new addition.

**Hints**
Here are some hints to help you achieve the desired functionality:

1. **Event Listener**: You'll need to add an event listener to the form element that listens for a specific event.

2. **Prevent Default**: Inside the event listener, use the `preventDefault()` method to prevent the default form submission behavior, as you want to handle the form submission yourself.

3. **Retrieve Input Values**: Use the `querySelector` method to retrieve the values of the input fields (Name and Marks) from the form when the submit button is clicked.

4. **Generate Serial Number (SNO)**: Calculate the serial number (SNO) for the new row. You can do this by counting the number of existing rows and incrementing it by 1 for the new row.

5. **Create New Elements**: Create new HTML elements for the new row (e.g., create a `<tr>` element with three `<td>` elements inside).

6. **Insert the New Row**: Use the appropriate methods to insert the newly created row (with the SNO, Name, and Marks) into the table's `<tbody>`.

7. **Clear Form**: Optionally, you can clear the form fields after the data is added to the table to provide a better user experience.

8. **Testing**: It's important to test your code to ensure that it works as expected. Verify that new rows are added to the table with the correct data when the form is submitted.

By following these hints and using the provided solution as a reference, you should be able to create a script that adds form input data to the table as described in the problem.

**Solution Approach**
Here's the step-by-step approach with code for adding form input data to a table in a boilerplate HTML structure:

1. **Select the Form and Add an Event Listener**:
   - Select the form element.
   - Add an event listener for the "submit" event.

```javascript
document.addEventListener("DOMContentLoaded", function () {
  const form = document.querySelector("form");
  form.addEventListener("submit", function (e) {
    e.preventDefault(); // Prevent default form submission behavior

    // Your code for the following steps goes here
  });
});
```

2. **Retrieve Input Values**:
   - Retrieve the values entered by the user in the Name and Marks input fields.

```javascript
const name = document.querySelector("#name").value;
const marks = document.querySelector("#marks").value;
```

3. **Calculate SNO**:
   - Determine the SNO by counting the number of rows already present in the table's `<tbody>`.

```javascript
const tableBody = document.querySelector("table tbody");
const sNo = tableBody.children.length + 1;
```

4. **Create New Row**:
   - Create a new row (`<tr>`) element.
   - Inside the new row, create three cell elements (`<td>`) for SNO, Name, and Marks.
   - Populate the cell elements with the values obtained from user input.

```javascript
const newRow = document.createElement("tr");
newRow.innerHTML = `
    <td>${sNo}</td>
    <td>${name}</td>
    <td>${marks}</td>
`;
```

5. **Insert the New Row**:
   - Append the newly created row to the table's `<tbody>`.

```javascript
tableBody.appendChild(newRow);
```

6. **Clear the Form**:
   - Optionally, you can clear the form fields to provide a better user experience.

```javascript
form.reset();
```

With this code, you'll be able to add form input data to the table in your boilerplate HTML structure.

**Solution**

```javascript
let form = document.querySelector("form");
form.addEventListener("submit", function (e) {
  e.preventDefault();
  let marks = document.querySelector("#marks").value;
  let name = document.querySelector("#name").value;
  let sNo = document.querySelectorAll("tbody tr").length + 1;
  let tr = document.createElement("tr");
  tr.innerHTML = `<td>${sNo}</td>
            <td>${name}</td>
            <td>${marks}</td>`;
  let tbody = document.querySelector("tbody");
  tbody.append(tr);
});
```
