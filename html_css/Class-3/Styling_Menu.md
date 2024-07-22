**Raw Problem**
You are provided with HTML and some preset CSS of a **Menu Card for a restaurant.**

**Write internal CSS** to add the below-mentioned styles to the Menu card.

**For the div.card:**

1. Set the height and width as 400px each
2. Apply a border of solid style, 30px width, and #7D5A44 color.
3. Set the background-color to #EBE0C7
4. Set line-height to 25px
5. Add a box-shadow of '0 10px 22px 10px rgba(27, 38, 49, 0.1)'
6. Set color property to #7D5A44

Now, in the h1 tag there is a <span> that contains the text '(Menu)'

**For the entire h1:**

1. Set text-align as 'center'
2. Add padding of 20px

**For the content in h1 inside of <span>, i.e., '(Menu)':**

1. Set text-decoration property to 'overline'
2. Set the font-size to 15px

_Don't make any changes to the HTML and CSS boilerplate code._

Further, **refer to the test cases** to understand necessary requirements to submit the problem.

The end result should be similar to the one given below:

![menu-hint-image](https://i.postimg.cc/s28KkZYW/mennu-hint-image.png)

**Hints**

1. Pay attention and follow every instruction in the problem description and test cases.
2. Use `.card h1` as a selector to select the entire h1,  
   and under this selector apply the styles required for content in the entire h1.
3. Use `.card h1 span` as a selector to select the span inside of h1,  
   and under this selector, apply the respective styles required.

**Solution Approach**
The approach to this solution is simple and straightforward. The learner has to follow the instructions provided in the problem description step by step and utilize CSS concepts like selectors and styling properties to add styles to the feature card.

Make use of the hints provided to understand the approach utilized with the concept of selector specification:

- Use `.card h1` as a selector to select the entire h1, and under this selector, apply the styles required for the content in the entire h1.
- Use `.card h1 span` as a selector to select the span inside of h1, and under this selector, apply the respective styles required.

It's important to pay attention to the details in the instructions and test cases.

**Solution**

```css
div.card {
  height: 400px;
  width: 400px;
  line-height: 25px;
  color: #7d5a44;
  border: 30px solid #7d5a44;
  background-color: #ebe0c7;
}

div.card h1 {
  text-align: center;
  padding: 20px;
}

div.card h1 span {
  text-decoration: overline;
  font-size: 15px;
}
```
