**Raw Problem**

You need to write a JS program that:

When the add button (`div.add-btn`) is clicked, it
makes the input modal (`div.modal-cont`) visible.

**Visible** means:

- display is set to `flex`

**Not Visible** means:

- display is set to `none`

Write the code in the `script.js` file, and utilize a boolean flag to manage states for when the modal is visible and not visible.

**Hints**

1. **Variable Declarations:**

   - There are three variable declarations: `addBtn`, `modalCont`, and `addFlag`.
   - `addBtn` is likely a reference to a button with a class of "add-btn".
   - `modalCont` is likely a reference to a modal container with a class of "modal-cont".
   - `addFlag` is a boolean variable used to track the state of whether the modal should be displayed or hidden.

2. **Event Listener Setup:**

   - An event listener is set up on the `addBtn` element.
   - The event being listened for is a "click" event on the button.

3. **Toggle Flag:**

   - When the "addBtn" is clicked, the `addFlag` is toggled between `true` and `false`.
   - This toggle is achieved by negating the current value of `addFlag` (`!addFlag`).

4. **Conditional Statement:**

   - There is a conditional statement (`if` statement) that checks the value of `addFlag`.
   - If `addFlag` is `true`, the style of `modalCont` is adjusted to make it visible (e.g., `flex` display).
   - If `addFlag` is `false`, the style of `modalCont` is adjusted to hide it (e.g., `none` display).

5. **Toggle Modal Visibility:**
   - The code effectively toggles the visibility of the modal container based on the state of `addFlag`.
   - If `addFlag` is `true`, the modal is displayed; if `addFlag` is `false`, the modal is hidden.

By understanding these hints, you should have a clearer picture of how the code manages the visibility of the modal container in response to the button click.

**Solution Approach**

### Step 1: Select Elements

Use `document.querySelector` to select the button (`addBtn`) and the modal container (`modalCont`). Ensure that the classes specified in the query selectors match the actual classes used in your HTML.

```javascript
let addBtn = document.querySelector(".add-btn");
let modalCont = document.querySelector(".modal-cont");
```

### Step 2: Set Initial State

Declare a boolean variable (`addFlag`) to track the state of the modal visibility. Set it to `false` initially.

```javascript
let addFlag = false;
```

### Step 3: Add Event Listener

Use `addEventListener` to listen for the "click" event on the `addBtn`. When the button is clicked, a callback function is executed.

```javascript
addBtn.addEventListener("click", function () {
  // Code inside the event listener will be executed when the button is clicked.
});
```

### Step 4: Toggle the Flag

Inside the event listener, toggle the value of `addFlag` using the logical NOT operator (`!`). This flips the boolean value between `true` and `false`.

```javascript
addFlag = !addFlag;
```

### Step 5: Adjust Modal Visibility

Use an `if` statement to check the value of `addFlag`. If `addFlag` is `true`, set the `display` property of `modalCont` to "flex" (or any other appropriate value for displaying). If `addFlag` is `false`, set it to "none" (or any value for hiding).

```javascript
if (addFlag) {
  modalCont.style.display = "flex";
} else {
  modalCont.style.display = "none";
}
```

### Step 6: Final Code

Combine all the steps into the final JavaScript code:

```javascript
let addBtn = document.querySelector(".add-btn");
let modalCont = document.querySelector(".modal-cont");
let addFlag = false;

addBtn.addEventListener("click", function () {
  addFlag = !addFlag;

  if (addFlag) {
    modalCont.style.display = "flex";
  } else {
    modalCont.style.display = "none";
  }
});
```

Make sure to replace the class names and adjust styles as needed based on your HTML and design. This code creates a toggle effect, showing and hiding the modal container when the button is clicked.

**Solution**

```javascript
let addBtn = document.querySelector(".add-btn");
let modalCont = document.querySelector(".modal-cont");

let addFlag = false;

addBtn.addEventListener("click", function () {
  addFlag = !addFlag;

  if (addFlag == true) {
    modalCont.style.display = "flex";
  } else {
    modalCont.style.display = "none";
  }
});
```
