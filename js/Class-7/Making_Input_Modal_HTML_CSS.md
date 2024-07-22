**Raw Problem**

Your task is to write CSS for the modal to create a new ticket.

You have been given HTML and CSS boilerplate code and you have to apply the below CSS rules:

### `.modal-cont` should have:

1. display of `flex`
2. background color of `lightblue`
3. height of `300px` and width of `500px`

### `.priority-colors-container` should have:

1. display of `flex`
2. flex direction of `column`
3. align items is set to `center`
4. justify content is set to `space-around`

**Solution Approach**
Modal Container Styles:

Create a class named .modal-cont for the modal container.
Set the height and width of the modal container to 300px and 500px respectively.
Set the background color of the modal container to light blue using the background property.
Use display: flex to make it a flex container.

Priority Colors Container Styles:

Create a class named .priority-colors-container for the container inside the modal.
Set the display property to flex to make it a flex container.
Use flex-direction: column to arrange the child items in a column.
Use align-items: center to center the child items along the horizontal axis.
Use justify-content: space-around to distribute the child items evenly along the vertical axis with space around them.

**Solution**

```css
.modal-cont {
  height: 300px;
  width: 500px;
  background: lightblue;
  display: flex;
}

.priority-colors-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
}
```
