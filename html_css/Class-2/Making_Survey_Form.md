**Raw Porblem**
Create an HTML form for a survey to collect information about the favourite food of people.

The survey should include the following fields:

- Name (text input)
- Age (number input)
- Gender (radio buttons with Male and Female options)
- Favorite Food (drop-down list with options like Pizza, Chinese food, Indian food, etc.)
- Do you like to cook? (checkbox with Yes/No options)
- Additional comments (textarea input)
- Submit button

Further, refer to the test cases to understand necessary requirements to submit the problem.

Below is the basic structure of the expected output:

![hint-image](https://raw.githubusercontent.com/mrinal1224/Scaler-Frontend-questions-Beginner-Module/main/class-2/question-2/hint-image.PNG)

**Hints**

1. Use the appropriate input type for each field.
2. Use labels to associate each field with its respective input element.
3. The form should have an action attribute that specifies where the form data should be sent when submitted.
4. The form should have a method attribute that specifies how the form data should be submitted.

**Solution Approach**
Start by creating the basic structure of the form using the <form> element.
Add a text input for the name field and associate it with a label.
Add a number input for the age field and associate it with a label.
Add radio buttons for the gender field and associate them with a label.
Add a drop-down list for the favorite food field and associate it with a label.
Add a checkbox for the "Do you like to cook?" field and associate it with a label.
Add a textarea for the additional comments field and associate it with a label.
Add a submit button to submit the form data.
Add the action and method attributes to the form.

**Solution**

```html
<body>
  <h1>Survey Form</h1>
  <form>
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required />

    <label for="age">Age:</label>
    <input type="number" id="age" name="age" required />

    <label for="gender">Gender:</label>
    <input type="radio" id="male" name="gender" value="male" required />
    <label for="male">Male</label>
    <input type="radio" id="female" name="gender" value="female" />
    <label for="female">Female</label>

    <label for="food">Favorite Food:</label>
    <select id="food" name="food" required>
      <option value="pizza">Pizza</option>
      <option value="chinese">Chinese food</option>
      <option value="indian">Indian food</option>
      <option value="mexican">Mexican food</option>
    </select>

    <label for="cook">Do you like to cook?</label>
    <input type="checkbox" id="cook" name="cook" />
    <label for="cook">Yes</label>

    <label for="comments">Additional comments:</label>
    <textarea id="comments" name="comments"></textarea>

    <input type="submit" value="Submit" />
  </form>
</body>
```
