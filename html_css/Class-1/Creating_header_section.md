**Raw Problem**  
Create a simple Nav bar and Header section using plain HTML.

For the nav bar:

1. Use `<a>` tags to add the redirectable links.

For the header section:

1. Use `<img>` tag to add a person's image.
2. Use Heading tags to add the name and summary/title.
3. Use the Button tag to add a button to download the resume.

**WARNING:** Don't use links in href or src properties, add "#" as mock link or use 'profile-img.jpg' for img src.

Further, refer to the test cases to understand necessary requirements to submit the problem.  
Below is the basic structure of the expected output:  
![hint-image](https://raw.githubusercontent.com/pantchayan/Scaler-Frontend-questions-Beginner-Module/5d29263117fbf4fc29a7b4568b921bc5e077dc07/class-1/question-1/hint-image.PNG)

**Hints**

1. Use <a> tags for the redirectable options in Nav bar.
2. Use the <img> tag to add an image to the webpage.
3. Use the 'src' and 'alt' attributes of the <img> tag to specify the source and alternate text of the image respectively.

**Solution Approach**
Start by creating the basic structure of the HTML document using the `<html>`, `<head>`, and `<body>` tags.

Add a `<header>` section that will contain the Nav bar and Necessary Details about the person.

Inside `<header>` section add two `<div>` tags, one for Nav bar and other for person details.

Use 4 `<a>` tags in Nav bar `<div>` to specify 4 redirectable options.

Add person's image in second `<div>` using `<img>` tag with proper 'src' and 'alt' attributes.

Use `<h1>`, `<h2>`, `<h3>` tags to specify person's Name, Intro, Description heading respectively.

Finally, use `<button>` tag to add a button to download resume.

**Solution**

```html
<body>
  <header>
    <!-- Navigation -->
    <div>
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Projects</a>
      <a href="#">Blog</a>
    </div>

    <!-- Necessary Details -->
    <div>
      <img src="profile-img.jpg" alt="Profile Image" />
      <h1>{PERSON_NAME}</h1>
      <h2>I'm a Frontend<br /><span>Developer</span></h2>
      <h3>Description:</h3>
      <button>DOWNLOAD RESUME</button>
    </div>
  </header>
</body>
```
