**Problem Description**
You are given an object user with a method getFullName that needs to return the full name of the user.
Use the 'this' keyword to access the object properties inside the method.

Test Cases -

```js
const user = {
  firstName: "John",
  lastName: "Doe",
  getFullName: "Function code goes here",
};
console.log(user.getFullName()); // Output: John Doe
```

**Hints**

- Use the 'this' keyword to access the object properties inside the method.

**Solution**

```js
const user = {
  firstName: "John",
  lastName: "Doe",
  getFullName: function () {
    return this.firstName + " " + this.lastName;
  },
};
```
