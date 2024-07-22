**Raw Problem**

The given JS code is broken. This is because:

Even when yellow box is clicked, it is alerted that red is clicked.

Fix the code such that:

1. It alerts as 'yellow is clicked' when yellow box is clicked.
2. and alerts as 'red is clicked' when the red box is clicked.
3. A single alert is generated when any of the boxes is clicked.

**Hints**

1. Use 'click' eventListener to each of the boxes (divs with 'red' and 'yellow' classes).
2. Use `window.alert('desired_msg')` to generate an alert.
3. To prevent red alert, utilize a boolean flag to keep account of when the yellow box is clicked.

**Solution Approach**

```html
<script>
  let redDiv = document.querySelector(".red");
  let yellowWasClicked = false;

  // Use 'click' eventListener to each of the boxes
  redDiv.addEventListener("click", (e) => {
    if (yellowWasClicked) {
      yellowWasClicked = false;
    } else {
      // Use window.alert('desired_msg') to generate an alert
      window.alert("red is clicked");
    }
  });

  let yellowDiv = document.querySelector(".yellow");
  yellowDiv.addEventListener("click", (e) => {
    yellowWasClicked = true;
    window.alert("yellow is clicked");
  });
</script>
```

**Solution**

```html
<script>
  // FIXED CODE =====
  let redDiv = document.querySelector(".red");
  let yellowWasClicked = false;

  redDiv.addEventListener("click", (e) => {
    if (yellowWasClicked) {
      yellowWasClicked = false;
    } else {
      window.alert("red is clicked");
    }
  });

  let yellowDiv = document.querySelector(".yellow");
  yellowDiv.addEventListener("click", (e) => {
    yellowWasClicked = true;
    window.alert("yellow is clicked");
  });
</script>
```
