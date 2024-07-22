**Raw Problem**  
Create an **About me Section** that contains the person's image, necessary heading, intro, description, and social profile links.

Use the following tags in proper flow:

1. `<section>` tag, to hold the entire about me section.
2. `<img>` tag with relevant src and alt attribute to add an image.
3. `<h1>` and `<h3>` tag for section heading and person's intro.
4. `<p>` tag for a long description.
5. `<a>` tags with enclosed `<img>` tags to have logos (images) of different social profiles as redirectable links.

Further, refer to the test cases to understand necessary requirements to submit the problem.

Below is the basic structure of the expected output:
![hint-image](https://d2beiqkhq929f0.cloudfront.net/public_assets/assets/000/056/376/original/about_me.PNG?1699530300)

**Hints**
Use the `<section>` tag that contains all the About Me components described.

Use the `<img>` tag to add a profile image to the section.

Use the 'src' and 'alt' attributes of the `<img>` tag to specify the source and alternate text of the image respectively.

Use the `<h1>` tag for heading.

Use the `<h3>` tag for intro.

Use the `<p>` tag for description text.

Use `<a>` tags with enclosed `<img>` tags to add links to social profiles with relevant logos.

**Solution Approach**
Start by creating the basic structure of the HTML document using the `<html>`, `<head>`, and `<body>` tags.

Add a `<section>` that will contain all the About Me components.

To add person's image, utilize the `<img>` tag with proper 'src' and 'alt' attributes.

Use `<h1>`, `<h3>`, and `<p>` tags to specify heading, intro, and description text respectively.

Use multiple `<a>` tags with enclosed `<img>` tags to add links to social profiles with relevant logos.

Further, you can divide and group different components under `<div>` tags as a good coding practice.

**Solution**

```html
<body>
  <!-- About Me section -->
  <section>
    <!-- Profile Image -->
    <div>
      <img src="profile-img.jpg" alt="Profile Image" />
    </div>

    <!-- Intro, Description and Links -->
    <div>
      <h1>About Me</h1>
      <h3>Hello! I'm {PERSON_NAME}</h3>
      <p>Description Area for About me</p>

      <!-- Links to social profiles along with logos -->
      <div>
        <a href="#"><img src="logo1.jpg" alt="Logo1" /></a>
        <a href="#"><img src="logo2.jpg" alt="Logo2" /></a>
        <a href="#"><img src="logo3.jpg" alt="Logo3" /></a>
        <a href="#"><img src="logo4.jpg" alt="Logo4" /></a>
      </div>
    </div>
  </section>
</body>
```
