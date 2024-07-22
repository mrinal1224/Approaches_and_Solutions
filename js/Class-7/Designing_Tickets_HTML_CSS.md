**Raw Problem**

Your task is to write CSS for the ticket.

You have been given HTML boilerplate code and you have to apply the below CSS rules:

### `.main-cont` should have:

1. display of `flex`
2. gap property set to `2rem`
3. padding of `2rem`
4. main-axis items are centered

### `.ticket-cont` should have:

1. height of `12rem`
2. width set to `15rem`
3. background color set to `coral`

### `.ticket-color` should have:

1. height of `1rem`

### `.ticket-id` should have:

1. background color of `yellow`
2. height as `2rem`

**Solution Approach**
Container Styles:
Create a container class named .main-cont.
Set the display property to flex.
Add a gap between the flex items using the gap property.
Center the content horizontally using justify-content: center.
Add padding to the container using padding: 2rem.
Allow the flex items to wrap to the next line with flex-wrap: wrap.

Ticket Container Styles:
Create a class named .ticket-cont for the ticket container.
Set the height and width of the ticket container to 12rem and 15rem respectively.
Set the background color of the ticket container to coral.

Ticket Color Bar Styles:
Create a class named .ticket-color for the color bar within the ticket container.
Set the height of the color bar to 1rem.

Ticket ID Styles:
Create a class named .ticket-id for the ticket ID section within the ticket container.
Set the background color of the ticket ID section to yellow.
Set the height of the ticket ID section to 2rem.

**Solution**

```css
.main-cont {
  display: flex;
  gap: 2rem;
  justify-content: center;
  padding: 2rem;
  flex-wrap: wrap;
}

.ticket-cont {
  height: 12rem;
  width: 15rem;
  background-color: coral;
}

.ticket-color {
  height: 1rem;
}

.ticket-id {
  background-color: yellow;
  height: 2rem;
}
```
