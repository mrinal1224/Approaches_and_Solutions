**Raw Problem**

You need to create a styled box element with specific dimensions and styles.

Create a div element with add class "styled-box" on it. Write internal CSS and use class selector to target the div and follow the below instructions to style the div:

1. Style the div element with the class styled-box to have a fixed width of 200px and a fixed height of 100px.
2. Set a background color of 'red' for the box.
3. Add a 20px margin around all sides of the box.
4. Apply a 10px padding to the box.
5. Add a solid border with a 5px width and black color.

_Refer to test cases in order to submit the problem successfully._

**Hints**

- Create a simple `div` and add class `.styled-box`
- Write internal CSS by adding `style` tag directly in the `head` of HTML.
- Follow the CSS requirements to add styles

**Solution Approach**

- Create a simple `div` and add class `"styled-box"`.
- Add `<style>` in the `head` of the HTML.
- Target the `div` with `.styled-box`
- Add width, height, padding, margin, and border for `.styled-box`

**Solution**

```css
.styled-box {
  width: 200px;
  height: 100px;
  background-color: red;
  margin: 20px;
  padding: 10px;
  border: 5px solid black;
}
```
