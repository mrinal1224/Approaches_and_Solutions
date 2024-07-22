**Raw Problem**
You are tasked with creating two overlapping elements using CSS positioning and write internal CSS following the following instructions:

1. Style the first div element with the class `element1` to have a fixed width and height of 100px each.
2. Apply a background color of your choice to `element1`.
3. Position `element1` 20px from the top and 20px from the left of its containing element.
4. Style the second div element with the class `element2` to have a fixed width and height of 80px each.
5. Apply a different background color to `element2`.
6. Position `element2` so that it overlaps `element1` by 10px from the top and 10px from the left of its containing element.

Refer the below image to see what is the end state we want to reach.

![ref-img](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/052/434/original/q3-img.png?1696454191)

**Hints**

1. Remember that CSS positioning can be used to control the placement of elements on the page.
2. Explore the position property and its values to decide how to position the elements.
3. Think about how to create the overlap effect by adjusting the top and left properties.

**Solution Approach**
To achieve the overlapping effect, follow these steps:

1. Style `element1` with a specific width, height, background color, and set its position property to `absolute`.
2. Use the `top` and `left` properties to position `element1` 20px from the top and 20px from the left of its containing element.
3. Style `element2` similarly with a different width, height, background color, and set its position property to `absolute` as well.
4. Adjust the `top` and `left` properties for `element2` to make it overlap `element1`.

**Solution**

```css
.element1 {
  width: 100px;
  height: 100px;
  background-color: #3498db;
  position: absolute;
  top: 20px;
  left: 20px;
}

.element2 {
  width: 80px;
  height: 80px;
  background-color: #e74c3c;
  position: absolute;
  top: 10px;
  left: 10px;
}
```
