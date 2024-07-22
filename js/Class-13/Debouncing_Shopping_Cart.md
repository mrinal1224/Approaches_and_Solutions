**Raw Problem**

**Debounce-Enabled Shopping Cart**

In this coding exercise, you will implement a debounce mechanism to enhance the shopping cart functionality of a web page. Currently, when a user clicks on the "Buy" button of a product multiple times in quick succession, the product gets added to the cart repeatedly. This behaviour is not ideal for a real e-commerce site. Your task is to modify the code to ensure that the product is added to the cart only once, even if the user clicks the "Buy" button multiple times in rapid succession.

**Instructions:**

1.  You are provided with an HTML document that contains a list of products, each with a "Buy" button displaying the product's price.
2.  The initial code sets up event listeners on each "Buy" button to add the corresponding product's price to the total cart value. However, this leads to unwanted behavior when the user rapidly clicks on a button.
3.  To address this, implement a debounce mechanism using a debounce function. This function takes two arguments: the event handler function and a delay in milliseconds. It ensures that the event handler is triggered only after the user stops interacting for the specified delay.
4.  Inside the loop that iterates over the "Buy" buttons, update the event listener to use the debounced event handler for processing clicks.
5.  Test your implementation by clicking on the "Buy" buttons rapidly. Verify that the product is added to the cart only once, regardless of how quickly the user clicks.

**Note:**

Remember that debounce is a common technique to improve user experience in scenarios like search inputs, button clicks, and other interactions where rapid consecutive actions might lead to undesired results.

**Hints:**

- You need to incorporate the debounce function correctly into the existing code.
- Pay attention to how the debounced event handler is passed to the addEventListener method.
- The goal is to ensure that the user's rapid clicks do not result in multiple additions of the same product to the cart. The debounce mechanism will allow the cart to update only once when the user pauses between clicks.

**Solution Approach: Debounce-Enabled Shopping Cart**

To implement the debounce mechanism for the shopping cart functionality, follow these steps:

1. **Understanding Debounce Function:**
   Before proceeding, understand how the provided `debounce` function works. It accepts a function and a delay as arguments and ensures that the function is executed only after the user stops interacting for the specified delay.

```javasript
        function debounce(fn, delay) {
            let timeoutId;
            return function (...args) {
                if (timeoutId) {
                    clearTimeout(timeoutId);
                    console.log(1);
                }
                timeoutId = setTimeout(function () {
                    fn(...args);
                }, delay);
            };
        }
```

2. **Incorporate Debounce:**
   Inside the loop that iterates over the "Buy" buttons, update the event listener to use the debounced event handler. Replace the existing event handler function with the debounced version. This ensures that the cart is updated only once, even if the user rapidly clicks on a button.

3. **Update Event Listener:**
   Modify the loop that iterates over the "Buy" buttons to replace the original event handler function with the debounced version. The modified code should look like this:

   ```javascript
   // Loop over "Buy" buttons
   for (let i = 0; i < btns.length; i++) {
     // Update event listener to use debounced event handler
     btns[i].addEventListener(
       "click",
       debounce(function (e) {
         let price = Number(btns[i].getAttribute("data-price"));
         tPrice += price;
         pricetext.innerText = tPrice;
       }, 500) // Specify the debounce delay (e.g., 500ms)
     );
   }
   ```

By following these steps, you will successfully implement a debounce mechanism for the shopping cart functionality. This will prevent multiple additions of the same product to the cart when the user clicks on the "Buy" button rapidly. The debounce mechanism enhances the user experience by providing more controlled and consistent behavior in scenarios where rapid consecutive actions can lead to undesired outcomes.

**Solution**

```javascript
function debounce(fn, delay) {
  let timeoutId;
  return function (...args) {
    if (timeoutId) {
      clearTimeout(timeoutId);
      console.log(1);
    }
    timeoutId = setTimeout(function () {
      fn(...args);
    }, delay);
  };
}
let tPrice = 0;
let btns = document.querySelectorAll("button");
let pricetext = document.querySelector("p span");
for (let i = 0; i < btns.length; i++) {
  btns[i].addEventListener(
    "click",
    debounce(function (e) {
      let price = Number(btns[i].getAttribute("data-price"));
      tPrice += price;
      pricetext.innerText = tPrice;
    }, 500)
  );
}
```
