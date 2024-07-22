**Raw Problem**
The goal of this problem is to use CSS to style a webpage with different colors.

Write CSS to change the:

1. Color of `h1` element to 'blue'
2. Background color of `p` element to 'rgb(255,255,0)'
3. Color of element with 'highlight' class to '#ff0000'
4. Background color of element with 'special' id to 'hsl(120, 100%, 50%)'
5. Background color of `input` element to 'rgba(255, 0, 0, 0.5)'
6. Color of link (`a`) to 'hsla(0, 100%, 50%, 0.8)' when hovered over

Further, refer to the test cases to understand necessary requirements to submit the problem.

Below is the basic structure of the expected output:

![hint-image](https://github.com/pantchayan/Scaler-Frontend-questions-Beginner-Module/blob/main/class-3/question-2/hint-image.PNG?raw=true)

**Hints**
Use color keywords to set the color of text and background.
Use RGB values to specify colors using red, green, and blue values.
Use HEX values to specify colors using a combination of hexadecimal digits.
Use HSL values to specify colors using hue, saturation, and lightness values.
Use RGBA and HSLA values to set the opacity of colors.

**Solution Approach**
Identify the elements that need to be styled with different colors.
Decide on the type of color value to use for each element.
Write the CSS code to set the color of each element using the chosen color value.

**Solution**

```css
h1 {
  color: blue;
}

p {
  background-color: rgb(255, 255, 0);
}

.highlight {
  color: #ff0000;
}

#special {
  background-color: hsl(120, 100%, 50%);
}

input[type="text"] {
  background-color: rgba(255, 0, 0, 0.5);
}

a:hover {
  color: hsla(0, 100%, 50%, 0.8);
}
```
