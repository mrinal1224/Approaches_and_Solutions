**Raw Problem**

Write a paragraph "Scaler is an online transformative upskilling platform for working tech and business professionals. \*" Make the following changes using just HTML:

1. "online transformative" as bold.
2. "upskilling platform" as italic.
3. "and business" as strikethrough.
4. "\*" as superscript.

The result should look like below:

"Scaler is an **online transformative** _upskilling platform_ for working tech <del>and business</del> professionals. <sup>\*</sup>"

Note: Use test cases as hints to achieve the desired output.

**Hints**

- Define a `p` and write the text in it.
- Wrap content in `**` to make it bold.
- Wrap content in `*` to make it italic.
- Wrap content in `~~` to strikethrough it.
- Wrap content in `^` to define a superscript text.

**Solution Approach**

- Simply define a paragraph tag using `<p>` and mention the content in it.
- Whatever part of the content needs to be bold, wrap it in `<strong>`.
- Whatever part of the content needs to be italic, wrap it in `<i>`.
- Whatever part of the content needs to be strikethrough, wrap it in `<del>`.
- Whatever part of the content needs to be superscript, wrap it in `<sup>`.

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
    <p>
      Scaler is an <strong>online transformative</strong>
      <i>upskilling platform</i> for working tech
      <del>and business</del> professionals. <sup>*</sup>
    </p>
  </body>
</html>
```
