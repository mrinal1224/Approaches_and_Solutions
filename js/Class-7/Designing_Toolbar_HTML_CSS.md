**Raw Problem**

Your task is to write CSS for the toolbar.

You have been given HTML boilerplate code and you have to apply the below CSS rules:

### `.toolbox-cont` should have:

1. Background color set to `#4b4b4b`
2. display set as `flex`
3. align-items set as `center`

### `.toolbox-priority-cont` should have:

1. Background color set to `#3d3d3d`
2. display set as `flex`
3. align-items set as `center`
4. justify-content set as `space-evenly`

### `.action-btn-cont` should have:

1. Background color set to `#3d3d3d`
2. display set as `flex`

### `.action-btn-cont > *` should have:

1. display set as `flex`
2. align-items set as `center`
3. justify-content set as `center`
4. color set as `white`

**Solution Approach**
Toolbox Container Styles:

Create a class named .toolbox-cont for the toolbox container.
Set the background color to #4b4b4b.
Use display: flex to make it a flex container.
Use align-items: center to center the child items along the vertical axis.
Toolbox Priority Container Styles:

Create a class named .toolbox-priority-cont for the priority container inside the toolbox.
Set the background color to #3d3d3d.
Use display: flex to make it a flex container.
Use align-items: center to center the child items along the vertical axis.
Use justify-content: space-evenly to evenly distribute the child items along the horizontal axis.
Action Button Container Styles:

Create a class named .action-btn-cont for the action button container.
Set the background color to #3d3d3d.
Use display: flex to make it a flex container.
Action Button Child Items Styles:

Target the child elements of .action-btn-cont using .action-btn-cont > \*.
Set display: flex on the child items.
Use justify-content: center and align-items: center to center the content of the child items.
Set the text color to white using color: white.

**Solution**

```css
.toolbox-cont {
  background-color: #4b4b4b;
  display: flex;
  align-items: center;
}

.toolbox-priority-cont {
  background-color: #3d3d3d;
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}

.action-btn-cont {
  background-color: #3d3d3d;
  display: flex;
}

.action-btn-cont > * {
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}
```
