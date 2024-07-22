**Raw Problem**
The goal of this problem is to use CSS selectors to style a webpage.

Use relevant CSS selectors and properties to:

1. Change color of `h1` heading to 'blue' and center it horizontally to the page.
2. Change background color `<p>` with class 'highlight' to 'yellow'.
3. Change font size of `<p>` with id 'special' to 20 pixels.
4. Add a solid gray border of 10 pixels to input of type 'text'.
5. Change the color of `<a>` to 'red' when user hovers over it.

Further, refer to the test cases to understand necessary requirements to submit the problem.

Below is the basic structure of the expected output:

![hint-image](https://github.com/pantchayan/Scaler-Frontend-questions-Beginner-Module/blob/main/class-3/question-1/hint-image.PNG?raw=true)

**Hints**
Use type selectors to select HTML elements by their element type.
Use class selectors to select elements by their class attribute.
Use ID selectors to select elements by their id attribute.
Use attribute selectors to select elements based on the values of their attributes.
Use pseudo-class selectors to select elements based on their state or position.

**Solution Approach**
Identify the elements that need to be styled.
Determine the appropriate selector for each element.
Write the CSS code to style the elements using the selected selectors.

**Solution**

```css
h1 {
  color: blue;
  text-align: center;
}

.highlight {
  background-color: yellow;
}

#special {
  font-size: 20px;
}

input[type="text"] {
  border: 10px solid gray;
}

a:hover {
  color: red;
}
```
