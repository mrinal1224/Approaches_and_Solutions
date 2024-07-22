**Raw Problem**  
Create a basic HTML webpage with 2 links.

1. Link should redirect to "www.interviewbit.com" on the same tab. Link text should be "Interview Bit".
2. Link should redirect to "www.scaler.com" on a different tab. Link text should be "Scaler".

**Hints**

- Use Anchor tags (`<a></a>`) to create links.
- Set destination using the `href` attribute.
- To open a link in a new tab, use the attribute `target='_blank'`.

**Solution Approach**

- Start by creating the basic structure of the HTML document using the `<html>`, `<head>`, and `<body>` tags.
- Add 2 links using anchor tags and the provided required text contents. Then use the `href` attribute to indicate the link's destination.
- Use the `target` attribute to specify where to open the linked document.

**Solution**

```html
<html>
  <body>
    <a href="https://www.interviewbit.com">Interview Bit</a>
    <a href="https://www.scaler.com" target="_blank">Scaler</a>
  </body>
</html>
```
