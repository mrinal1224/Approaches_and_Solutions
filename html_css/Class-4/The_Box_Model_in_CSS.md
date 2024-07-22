**Raw Problem**

Create a CSS web page that demonstrates the box model.

- The web page should display a box with a width of 400px, a height of 200px, and a border of 10px.
- The box should have a margin of 20px and a padding of 30px.
- The background color of the box should be lightgray.

Further, refer to the test cases to understand necessary requirements to submit the problem.  
Below is a basic look of the expected output:  
![hint-image](https://raw.githubusercontent.com/pantchayan/Scaler-Frontend-questions-Beginner-Module/main/class-4/question-1/hint-image.PNG)

**Hints**
Use the width and height properties to set the width and height of the box.
Use the border property to add a border to the box.
Use the margin and padding properties to add a margin and padding to the box.
Use the background-color property to set the background color of the box.

**Solution Approach**
Create a container element to display the box.
Set the width and height of the box using the width and height properties.
Add a border to the box using the border property.
Add a margin and padding to the box using the margin and padding properties.
Set the background color of the box using the background-color property.

**Solution**

```css
.box {
  width: 400px;
  height: 200px;
  border: 10px solid black;
  margin: 20px;
  padding: 30px;
  background-color: lightgray;
}
```
