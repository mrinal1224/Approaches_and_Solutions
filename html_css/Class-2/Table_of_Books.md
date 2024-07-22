**Raw Problem**

Create an HTML table to display information about 5 different books.  
The table should have a header row and 4 data rows.  
Each book should have a title, author, publication date, and number of pages.

Below is the basic structure of the expected output:

![Basic Structure](https://raw.githubusercontent.com/pantchayan/scaler-portal-questions/b77c99ea17b994bdcb32fc81de8134a8d552cc22/module-1/class-2/front-end-HTML-4/hints/image.png)

**Hints**
Use the `table` element to create the table structure.  
Use the `thead` and `tbody` elements to create the header and data sections of the table.
Use the tr element to create a row and the td element to create a data cell.

**Solution Approach**
Create the HTML structure of the table using the table, thead, tbody, tr, and td elements.
Add the header information to the table using the th element inside the header row.
Add the data for the 5 books to the table.

**Solution**

```html
<body>
  <table>
    <thead>
      <tr>
        <th>Title</th>
        <th>Author</th>
        <th>Publication Date</th>
        <th>Pages</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>The Great Gatsby</td>
        <td>F. Scott Fitzgerald</td>
        <td>April 10, 1925</td>
        <td>180</td>
      </tr>
      <tr>
        <td>To Kill a Mockingbird</td>
        <td>Harper Lee</td>
        <td>July 11, 1960</td>
        <td>281</td>
      </tr>
      <tr>
        <td>1984</td>
        <td>George Orwell</td>
        <td>June 8, 1949</td>
        <td>326</td>
      </tr>
      <tr>
        <td>Pride and Prejudice</td>
        <td>Jane Austen</td>
        <td>January 28, 1813</td>
        <td>282</td>
      </tr>
      <tr>
        <td>The Catcher in the Rye</td>
        <td>J.D. Salinger</td>
        <td>July 16, 1951</td>
        <td>277</td>
      </tr>
    </tbody>
  </table>
</body>
```
