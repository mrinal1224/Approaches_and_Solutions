**Raw Porblem**
Create a basic HTML webpage that displays 2 lists: one ordered and one unordered.

Ordered List should contain a list of 5 cities from around the world. Use alphabetic numbers for the list-item marker.

Unordered List should contain a list of 3 beverages. Use square for the list-item marker.

Note: Use test cases as hints to achieve the desired output.

**Hints**

- Use the `<ol>` tag to create the ordered list wrapper.
- Use the `<ul>` tag to create the unordered list wrapper.
- Use the `<li>` tag to mention each item.
- Use the `type` attribute to change the list-item marker for ordered lists.

**Solution Approach**

- Start by creating the basic structure of the HTML document using the `<html>`, `<head>`, and `<body>` tags.
- Add an ordered list using the `<ol>` tag, and further add list items using the `<li>` tag. Use the `type` attribute set to `"a"` or `"A"` to change the list-item marker.
- Add an unordered list using the `<ul>` tag, and further add list items using the `<li>` tag. Use the `type` attribute set to `"square"` to change the list-item marker.

**Solution**

```html
<!DOCTYPE html>
<html>
  <body>
    <!-- "type" attribute could also have value "A" here -->
    <ol type="a">
      <li>City 1</li>
      <li>City 2</li>
      <li>City 3</li>
      <li>City 4</li>
      <li>City 5</li>
    </ol>
    <ul style="list-style-type: square;">
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ul>
  </body>
</html>
```
