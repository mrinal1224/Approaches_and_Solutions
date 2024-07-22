**Raw Problem**  
**Create a basic HTML website for Scaler.**  
The page should have:

- An image on the top for the Scaler logo.
- A heading that reads "Scaler Academy".
- One sentence description about Scaler.

Please note that:

- For the heading, use the `<h1>` tag.
- For the one-line description, use the `<p>` tag.
- You are provided with an image in the assets folder, named `logo.png`. Simply enter the `src` value as 'logo.png' to use it.

And finally, a link with text "Go to website" which points to Scaler's website in a new tab.

- The image's alternate text should be "scaler academy logo", and the width and height of the image should be 100px.

Note:  
It can be possible that the image provided above doesn't work on Scaler IDE. Please make sure to utilize the correct alt value.

**Hints**
Instructions:

- Add an image to your website using the `<img />` tag.
- Link the image to load through the `src` attribute, alternate text using the `alt` attribute, and set the width and height of the image through the `width` and `height` attributes.
- For the heading, use the `<h1>` tag.
- For the one-line description, use the `<p>` tag.
- For the link, use an anchor tag (`<a></a>`) with the `href` attribute pointing to Scaler's website.
- To open the link in a new tab, add the attribute `target="_blank"` to the anchor tag.

**Solution Approach**

- Start by creating the basic structure of the HTML document using the `<html>`, `<head>`, and `<body>` tags.
- Use the `src` attribute on the `<img>` tag to add the image to your webpage. Use the link mentioned in the question.
- Use the `alt` attribute on the `<img>` to add alternate text to your image, in case the browser fails to load your image due to some reason.
- Use `width` and `height` on the `<img>` to set "100px" width and height to your image.
- For the heading, use the `<h1>` tag and provide the text "Scaler Academy".
- Use the anchor tag to link to the Scaler website, indicate the destination using the `href` attribute and furthermore use the `target` attribute with the value `_blank`.

**Solution**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <img
      width="100px"
      height="100px"
      src="logo.png"
      alt="scaler academy logo"
    />
    <h1>Scaler Academy</h1>
    <p>This is scaler academy</p>
    <a href="https://www.scaler.com" target="_blank">Go to website</a>
  </body>
</html>
```
