**Raw Problem**

**Style a simple navigation menu.**  
You are provided with HTML of a navigation menu made using semantic tags like ul, li.

- On ul, change background colour to yellow.
- On li tag, apply space around the element's content by 20px, set font size as 20px and "display" property to inline-block.
- Also, remove the default list style using CSS.

Refer to test cases in order to submit the problem successfully.

Below is the image to see what is the end state we want to reach.  
![ref-img](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/052/433/original/q1-img.png?1696452753)

**Hints**
Make sure to set `list-style-type` property to none for `<ul>`.  
Add padding and font-size for li(s) to 20px.  
Align li(s) on the same line by setting the "display" property appropriately.

**Solution Approach**

- Start styling with padding and font-size as mentioned in the image.
- Add "list-style-type" property to "none" for ul tag and set background color to yellow.
- Align li(s) on the same line by setting "display" property to either block, inline, or inline-block.

**Solution**

```css
.nav {
  background-color: yellow;
  list-style-type: none;
  text-align: center;
  margin: 0;
  padding: 0;
}

.nav li {
  display: inline-block;
  font-size: 20px;
  padding: 20px;
}
```
