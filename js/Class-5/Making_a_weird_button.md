**Raw Problem**

A button of class `double` exists inside the parent div of id `#doubleHolder` in the HTML. Write a JavaScript program such that whenever the button is clicked:

1. It is destroyed (removed from the parent div)
2. Two new buttons are created in its place (inside the same parent div)
3. The new buttons should also inherit the same feature, making it a recursive feature.

**Hint:** Use the class of `double` and add the functionality to all the buttons having a class of `double` i.e., _All new buttons should also have `double` as class_

**Hints**

1. Add a 'click' eventListener to get the event when `double` button is clicked.
2. Use `createElement` method to create the new buttons.
   1. Use `setAttribute` to add class of `double` to these new buttons.
3. Use `appendChild` method to add the buttons to the parent div.
4. Use `removeChild` method to remove the double button from the parent div.

<!-- Solution Approach -->

```html
<script>
  // 1. Add a 'click' eventListener to get the event when double button is clicked.
  document
    .querySelector("#doubleHolder")
    .addEventListener("click", function (e) {
      if (e.target.classList.contains("double")) {
        // 2. Use createElement method to create the new buttons.
        let btn = document.createElement("button");
        btn.setAttribute("class", "double");
        btn.innerHTML = "double";

        let btn2 = document.createElement("button");
        btn2.setAttribute("class", "double");
        btn2.innerHTML = "double";

        // 3. Use appendChild method to add the buttons to the parent div.
        e.currentTarget.appendChild(btn);
        e.currentTarget.appendChild(btn2);

        // 4. Use removeChild method to remove the double button from the parent div.
        e.currentTarget.removeChild(e.target);
      }
    });
</script>
```

**Solution**

```html
<script>
  let dblHolder = document.querySelector("#doubleHolder");
  window.addEventListener("click", function (e) {
    if (e.target.classList.contains("double")) {
      e.target.remove();
      let button = document.createElement("button");
      button.setAttribute("class", "double");
      button.innerText = "double";
      dblHolder.appendChild(button);

      let button2 = document.createElement("button");
      button2.setAttribute("class", "double");
      button2.innerText = "double";
      dblHolder.appendChild(button2);
    }
  });
</script>
```
