**Raw Porblem**
Create a basic HTML webpage that displays a table like the one shown below:

![table image](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/050/630/original/q2-img.png?1695680016)

**Hints**

- Use a `<table>` tag to create a table. We can set the attribute to `border` if we want borders in our table.
- Use `<tr>` to define rows.
- Use `<th>` for table heading data.
- Use `<td>` for table data. We can use `rowspan` and `colspan` attributes to specify the number of rows or columns a cell should span.

**Solution Approach**

- Define a `<table>` tag to create a table. Add the `border` attribute to include borders.
- Define rows with `<tr>`, headings with `<th>`, and data items with `<td>`.
- For data to span across rows or columns, use `rowspan` and `colspan`.

**Solution**

```html
<!DOCTYPE html>
<html>
  <body>
    <table border>
      <tr>
        <th>Name</th>
        <th>Tech</th>
        <th>Rating</th>
      </tr>
      <tr>
        <td rowspan="2">Vikhyat</td>
        <td>HTML</td>
        <td>5</td>
      </tr>
      <tr>
        <td>CSS</td>
        <td>1</td>
      </tr>
      <tr>
        <td rowspan="2">Ayush</td>
        <td>HTML</td>
        <td>4</td>
      </tr>
      <tr>
        <td>CSS</td>
        <td>2</td>
      </tr>
      <tr>
        <td colspan="3">Total: 12</td>
      </tr>
    </table>
  </body>
</html>
```
