**Raw Problem**

**Problem Description:**  
Write a JS program to successfully make the given Counter function.

![counter-gif](https://i.postimg.cc/Gt8sNshj/counter-gif.gif)

The counter has **several components with dedicated functions**, here is the list for the same:

1. span#number => contains the current number value.
2. input#increment => field that takes the input for the increment number/factor. (default is 1)
3. button#add => when clicked updates the span#number by adding increment number to it.
4. button#subtract => when clicked updates the span#number by subtracting increment number from it.
5. button#reset => changes the span#number to 0 again.

Make sure the input for increment number is always parsed to Integer using parseInt(input).

Use the above information to write the entire JS program in the script.js file or script tag.  
Refer to the test cases to further understand the criteria to submit the problem successfully.

**Hints**

1. Use ID's to get the DOM reference of mentioned Elements

2. Maintain a global variable to keep account of the increment number/ factor.

3. add eventListener of 'change' to the input#increment and update the increment number/ factor in its callback. 4. add eventListener of 'click' to the buttons and update the span#number in their callbacks.

4. add eventListener of 'click' to the reset button and change the span#number to 0 in its callback.

5. Utilise parseInt('number_as_string') to change number as text to integer after accessing span#number's innerText.

**Solution Approach**
To implement the functionality described in the problem, we can follow a few simple steps. Firstly, we can use ID's to get the DOM reference of the mentioned elements. This will allow us to access these elements in our JavaScript code and manipulate them as needed.

Next, we can maintain a global variable to keep track of the increment number or factor. This variable can be initialized to a default value of 1 or any other desired value.

We can then add an eventListener of 'change' to the input#increment element. In its callback function, we can update the increment number or factor based on the value entered by the user in the input field.

Similarly, we can add eventListeners of 'click' to the buttons and update the span#number in their respective callback functions. To update the span#number, we can simply add or subtract the current increment number or factor from its current value.

Finally, we can add an eventListener of 'click' to the reset button. In its callback function, we can change the span#number to 0, effectively resetting the count.

To ensure that the numbers are treated as integers rather than strings, we can utilize the parseInt('number_as_string') method. This will convert the number as a string to an integer, allowing us to perform mathematical operations on it.

By following these steps, we can create a fully functioning counter on our web page that allows users to increment or decrement a number based on their desired factor, as well as reset the count as needed.

**Solution**

```js
let incrementField = document.getElementById("increment");
let addButton = document.getElementById("add");
let subtractButton = document.getElementById("subtract");
let resetButton = document.getElementById("reset");
let currValueHolder = document.getElementById("number");
let incrementNumber = 1;

incrementField.addEventListener("change", function (e) {
  incrementNumber = parseInt(e.target.value);
});

addButton.addEventListener("click", function (e) {
  let total = parseInt(currValueHolder.innerText) + incrementNumber;

  currValueHolder.innerText = total;
});

subtractButton.addEventListener("click", function (e) {
  let total = parseInt(currValueHolder.innerText) - incrementNumber;

  currValueHolder.innerText = total;
});

resetButton.addEventListener("click", function (e) {
  currValueHolder.innerText = 0;
});
```
