**Raw Problem**  
Create a Projects section where projects will be showcased with necessary headings, divs, and Images with project logos and project descriptions.

Use the following tags in proper flow:

1. `<section>` tag to hold all the content for the Projects Section
2. `<h1>` tag that holds the section heading of 'My Projects'
3. `<div>` tag that groups all the tags associated with a single project
4. For each project use:
   4.1 `<img>` tag for the project's image
   4.2 `<h2>` tag for the project's name
   4.3 `<p>` tag for the project's description

Further, refer to the test cases to understand necessary requirements to submit the problem.

Below is the basic structure of the expected output:  
![hint-image](https://raw.githubusercontent.com/pantchayan/Scaler-Frontend-questions-Beginner-Module/main/class-1/question-3/hint-image.PNG)

**Hints**
Use the `<section>` tag that contains all the projects' components.

Use the `<h1>` tag for section heading 'My Projects'.

Group all the components for each project in separate `<div>` tags.

Use the `<img>` tag to add a logo for the project.  
Use the 'src' and 'alt' attributes of the `<img>` tag to specify the source and alternate text of the image respectively.

Use the `<h2>` tag for project heading.

Use the `<p>` tag for project description.

**Solution Approach**
Start by creating the basic structure of the HTML document using the `<html>`, `<head>`, and `<body>` tags.

Add a `<section>` that will contain all the projects' components.

Use the `<h1>` tag to specify the heading for the section as 'My Projects'.

Add a `<div>` tag; this will contain all the required project components for a single project.

Inside the `<div>` tag, add `<img>`, `<h2>`, and `<p>` tags to specify the project's logo, heading, and description respectively.

Repeat the last two steps to add details for multiple projects.

You can further divide and group different components under `<div>` tags as a good coding practice.

**Solution**

```html
<body>
  <!-- Projects Section -->
  <section>
    <div>
      <h1>My Projects</h1>
      <p>I mostly work with HTML, CSS, JavaScript</p>

      <div>
        <div>
          <img src="" alt="Project1" />
          <h2>Project 1</h2>
          <p>Project 1 description.</p>
        </div>

        <div>
          <img src="" alt="Project2" />
          <h2>Project 2</h2>
          <p>Project 2 description.</p>
        </div>

        <div>
          <img src="" alt="Project3" />
          <h2>Project 3</h2>
          <p>Project 3 description.</p>
        </div>
      </div>
    </div>
  </section>
</body>
```
