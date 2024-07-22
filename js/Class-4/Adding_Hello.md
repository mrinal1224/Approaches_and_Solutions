**Raw Problem**  
Write a program in JS to do the below mentioned task:

When the button is clicked, append a `div` element, containing inner text 'Hello', as Child for the `body` element.

**Hints**
Use eventListener of 'click' on button.
Utilise createElement to create a new `div` element.
Use innerText property to set text as 'Hello'
Use querySelector and appendChild to add the `div` element to `body`

**Solution Approach**
To create a new `div` element with the text 'Hello' and append it to the `body` element when a button is clicked, you can use the following approach:

First, add an event listener of 'click' to the button using the addEventListener method. Inside the event listener function, create a new `div` element using the createElement method and store it in a variable.

Next, set the innerText property of the `div` element to 'Hello' using the dot notation.

Then, use querySelector to select the `body` element and append the new `div` element to it using the appendChild method.

**Solution**

```js
let btn = document.querySelector("button");

// 1. Use eventListener of 'click' on button.

btn.addEventListener("click", function () {
  console.log("button clicked");

  // 2. Utilise createElement to create a new <div> element

  let divElem = document.createElement("div");

  //create Element lets you Create a new Element in the DOM

  // 3. Use innerText property to set text as 'Hello'

  divElem.innerText = "Hello";

  // inner text is a property by which you can access and add or remove Text inside an element

  // 4. Use querySelector and appendChild to add the <div> element to <body>

  let bodyElem = document.querySelector("body");

  bodyElem.appendChild(divElem);

  // this method allows you to add new Children inside your selected element
});
```
