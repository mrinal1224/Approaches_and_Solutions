**Raw Problem**

**Problem Description:**

Write a JS program to make the given OTP input work properly.

![OTP-gif](https://i.postimg.cc/bJvnxB7W/OTP-gif.gif)

In the Document, you have div#inputs that contain 4 input fields with 'input' class.  
Here is how these inputs should work:

1. Each of the fields only takes a single-digit number as input.
2. When a number is entered, the focus moves to the next input field.
3. Pressing Backspace or Delete key removes the input of the current field, and the focus moves to the previous field.

You can utilise methods like isNan(value), Element.focus(), Element.nextElementSibling and Element.previousElementSibling to make the above-mentioned features work.

Use the above information to write the entire JS program in the script.js file or script tag.  
Refer to the test cases to further understand the criteria to submit the problem successfully.

NOTE:  
HTML and CSS are handled for you, please don't change the structure of the document.

**Hints**

1. Add eventListener of 'input' on div#inputs to track the inputs being made to children feilds.

2. In the call back of the above eventListener, utilise the event object to get the target Element. 3. Make use of the methods like isNan(value), Element.focus(), Element.nextElementSibling and Element.previousElementSibling on the target Element.

3. Add eventListener of 'keyup' to keep track of Backspace or Delete key being pressed.

4. Use isNan(value) to check if the input being made is a valid number or not.

**Solution Approach**

1. To create an OTP input field, we can utilize the DOM and event listeners to track user input and update the focus of the cursor accordingly.
2. We start by adding an event listener of 'input' on the parent div element, which allows us to track any input made to the child fields.
3. In the callback function of the event listener, we can use the event object to get the target element, and then use methods like isNaN() and nextElementSibling to ensure that the input is a valid number and move the focus to the next input field if it is.
4. We can also add a separate event listener of 'keyup' to track when the backspace or delete keys are pressed and clear the current input field while moving the focus back to the previous input field.
   With this approach, we can create a seamless and intuitive OTP input field that allows users to easily enter their verification code.

**Solution**

```js
const inputs = document.getElementById("inputs");

inputs.addEventListener("input", function (e) {
  const target = e.target;
  const val = target.value;

  if (isNaN(val)) {
    target.value = "";
    return;
  }

  if (val != "") {
    const next = target.nextElementSibling;
    if (next) {
      next.focus();
    }
  }
});

inputs.addEventListener("keyup", function (e) {
  const target = e.target;
  const key = e.key.toLowerCase();

  if (key == "backspace" || key == "delete") {
    target.value = "";
    const prev = target.previousElementSibling;
    if (prev) {
      prev.focus();
    }
    return;
  }
});
```
