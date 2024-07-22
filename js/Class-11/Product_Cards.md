\*\*Raw Problem\*\*

Write a JS program to display information of various products from a list.  
Read the entire problem description carefully to understand the necessary details.

![Product-cards-image](https://i.postimg.cc/zBPg0k5B/Product-Card-Image.png)

You are provided with: _(Don't make any changes to the below-mentioned files)_  
1\. **index.html** => containing basic document structure  
2. **styles.css** => contains styling  
3\. and **data.js** => has a data variable that contains an Array of Objects with details of several products.

As you can access the data array, your task is to  
write a program to make a product card for each of the product's objects inside this array.

**Algorithm:**  
1\. Traverse through the data Array.  
2\. Individually accessing each product's Object.  
3\. Inject relevant details like title, category, and rating count in the below-mentioned HTML template to make a div.card.  
4\. To make the rating stars:

4.1. Round off the rating.rate value of an object to the nearest Integer

4.2. Use this value to determine the number of empty and filled stars out of 5. (Ex: For a rating of 3/5 => 3 filled stars and 2 empty stars)

4.3. Utilise these values in a loop to make filled and empty stars

4.4. To make filled star symbol use a span tag with text as '&#9733;' and for empty star use '&#9734;'

4.5. Note that it is important to add class of 'star\_\_filled' and 'star\_\_notfilled' for respective cases. (To pass final test case)

4.5. Wrap these stars (span tags) inside a div with class 'all\_\_star'. The final result should be as shown below.

<div class="all\_\_star">

<span class="star\_\_filled">&#9733;</span>

<span class="star\_\_filled">&#9733;</span>

<span class="star\_\_filled">&#9733;</span>

<span class="star\_\_filled">&#9733;</span>

<span class="star\_\_notfilled">&#9734;</span>

</div>

5\. Finally, after the div.card is ready with all the details injected, add it to div#container

The **HTML structure of a card** is as follows: _(Use this directly as card's HTML template)_

<div class="card">

<div class="details">

<span class="product\_\_name">${product.title}</span>

<br>

<span class="product\_\_category">${product.category}</span>

<div class="all\_\_star">

${HTML FOR SPANS OF STARS (as discussed in step 4 of Algorithm)}

</div>

<div class="rating\_\_count">Rating Count : <span>${product.rating.count}</span></div>

</div>

<div class="btn">

<button class="btn\_\_buy">Buy Now</button>

</div>

</div>  
  
and **object inside the data array has the following structure**: _(Note that only a few of these values are required to be injected)_

```js
{
id: 1,

title: "Sample Product 1",

price: 109.95,

description:

"Your perfect pack for everyday use and walks in the forest. Stash your laptop (up to 15 inches) in the padded sleeve, your every day",

category: "men's clothing",

image: "https://fakestoreapi.com/img/81fPKd-2AYL.\_AC\_SL1500\_.jpg",

rating: {

rate: 3.9,

count: 120,},
}
```

Use the above information to write the entire JS program in the script.js file or script tag. (below the script tag loading data.js file)  
Refer to the test cases to further understand the criteria to submit the problem successfully.

Feel free to access hints to get help/assistance.

**Hints**
1\. Traverse on the data array to access individual object.

2\. Use document.createElement('div') to create a div that will hold all the spans containing individual stars.

3\. Follow the step 4 of algorithm and utilise 2 loops to add spans containing filled and empty stars to the above div.

**Solution Approach**

1. To create a dynamic card with star ratings for a list of products, we can utilize a loop to access individual objects in the data array.
2. Inside the loop, we can create a div element to hold all the spans containing the individual stars.
3. The next step is to add the filled and empty stars to this div using two loops as per the algorithm. We can then use a template literal to inject the values inside an HTML template that includes the star div.
4. This template can be added to the document inside the div with id "container" using document.getElementById('container').innerHTML += TEMPLATE.
5. The final code should include a loop to traverse the data array, the creation of the star div with filled and empty stars, injection of values into the HTML template, and appending the template to the document inside the container div.

**Solution**

```js
let container = document.getElementById("container");

data.forEach((val) => {
  let coloredRatingStar = parseInt(val.rating.rate);
  let notColoredRatingStar = 5 - coloredRatingStar;

  let allStarDiv = document.createElement("div");
  allStarDiv.setAttribute("class", "all__star");

  for (let i = 0; i < coloredRatingStar; i++) {
    allStarDiv.innerHTML += `<span class="star__filled">&#9733;</span>`;
  }

  for (let i = 0; i < notColoredRatingStar; i++) {
    allStarDiv.innerHTML += `<span class="star__notfilled">&#9734;</span>`;
  }

  container.innerHTML += `<div class="card">
      <div class="details">
        <span class="product__name">${val.title}</span><br>
        <span class="product__category">${val.category}</span>
        <div class="all__star">
          ${allStarDiv.innerHTML}
        </div>
        <div class="rating__count">Rating Count : <span>${val.rating.count}</span></div>
      </div>
      <div class="btn">
        <button class="btn__buy">Buy Now</button>
      </div>
    </div>`;
});
```
