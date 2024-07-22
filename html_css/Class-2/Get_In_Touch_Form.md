**Raw Porblem**
Create the **‘Get in Touch’** Form for your portfolio which should include the following:

1. Name input section (an input of text type)
2. Email input section (an input of email type)
3. Message input section (a textarea)
4. and a submit button (an input of submit type)

Further, refer to the test cases to understand necessary requirements to submit the problem.

Below is the basic structure of the expected output:

![hint-image](https://raw.githubusercontent.com/mrinal1224/Scaler-Frontend-questions-Beginner-Module/main/class-2/question-3/hint-image.PNG)

**Hints**

1. Use the <section> tag that contains the form.
2. Use the <h1> tag for section heading 'Get in Touch'.
3. Use the <form> tag to make the described form.
4. For name input use <input> tag with type as 'text'.
5. For email input use <input> tag with type as 'email'.
6. For message input use <textarea> tag.
7. For submit button use <input> tag with type as 'submit' and value as 'Send'.
8. Enclose the input tags in separate <label> tags.
9. Use <span> tag above <input> tags to add the description of input.
10. Specify relevant placeholders for each input.

**Solution Approach**
Start by creating the basic structure of the HTML document using the <html>, <head>, and <body> tags.
Add a <section> that will contain the 'Get in Touch' form.
Use <h1> tag to specify the heading for the section as 'Get in Touch'.
Use <form> tag to make the described form, further add three <label> tags that will enclose each text input.
For Name input, add <input> tag with attributes like type as 'text', name as 'name' and placeholder as 'Name' inside the first <label> tag, alongside a <span> containing 'Name'.
For Email input, add <input> tag with attributes like type as 'email', name as 'email' and placeholder as 'Email' inside the second <label> tag, alongside a <span> containing 'Email'.
For Message input, add <textarea> tag with attributes like name as 'message' and placeholder as 'Message' inside the third <label> tag, alongside a <span> containing 'Message'.
To add submit button, use <input> tag with attributes like name as 'submit', type as 'submit' and value as 'Send'.

**Solution**

```html
<body>
  <section>
    <h1>Get in Touch</h1>
    <form>
      <label>
        <span>Name</span>
        <input type="text" name="name" placeholder="Name" />
      </label>
      <label>
        <span>Email</span>
        <input type="email" name="email" placeholder="Email" />
      </label>
      <label>
        <span>Message</span>
        <textarea name="message" placeholder="Message"></textarea>
      </label>
      <input name="submit" type="submit" value="Send" />
    </form>
  </section>
</body>
```
