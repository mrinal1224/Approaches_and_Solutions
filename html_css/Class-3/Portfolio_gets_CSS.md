**Raw Problem**
Style your portfolio using CSS, for this question change the elements based on the following specifications:

1.  Change the font family of text to: 'Lato', sans-serif
2.  Change the color of Person's name's font to #5DA9E9
3.  Set the width of image in header section to : 400px

Note :
In the complete solution, after the above 3 specifications, we have further added more stylings for you to reference and add to your own portfolio.
However, to submit and pass the test cases you just need to implement the above-mentioned specifications.

**Hints**

1. Use concept of CSS selectors to grab the required HTML element.
2. Use concepts and properties like: font-family, color, width and CSS units.

**Solution Approach**
In the style.css file, use '\*' selector to select all the HTML elements and then set their font-family as 'Lato', san-serif.
Further use 'header h1' as selector to grab the font with Person's Name and set its color property as '#5DA9E9'.
At last select the image in header section using 'header img' and set its width property as '30%'.

**Solution**

```css
* {
  font-family: "Lato", sans-serif;
}

header a,
header h2,
header h3 {
  color: white;
}

header a {
  text-decoration: none;
  text-transform: uppercase;
}

header h1,
span,
button {
  color: #5da9e9;
}

header,
header button {
  background-color: black;
  border-color: #5da9e9;
  font-weight: 600;
}

header button:hover {
  background-color: #5da9e9;
  color: black;
  border-color: black;
  cursor: pointer;
}

header img {
  width: 400px;
}

section.about {
  background-color: white;
}

section.about img {
  width: 30%;
}

section.about a img {
  width: 3em;
}

section.projects {
  background-color: black;
}

.projects-head {
  color: white;
}

section.projects div.card {
  background-color: white;
  width: 20%;
}

section.projects div.card img {
  width: 3em;
}

section.projects div.card:hover {
  background-color: #5da9e9;
}

section.projects h2 {
  color: #5da9e9;
}

section.projects div.card:hover h2 {
  color: white;
}

.contact-section {
  background-color: white;
}

.contact-section * {
  width: 100%;
}

.contact-section h1,
.contact-section span {
  color: #5da9e9;
}

.contact-section #submit_button {
  background-color: #5da9e9;
}
```
