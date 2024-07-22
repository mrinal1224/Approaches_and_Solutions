**Problem Description**
Create a constructor function Person that takes name as a parameter and initializes the object with the provided name. Use the this keyword inside the constructor.

Test Cases

```js
const person1 = new Person("Alice");
console.log(person1.name); // Output: Alice
```

**Hints**

- Use the this keyword to access the object properties inside the constructor function.

**Solution**

```js
function Person(name) {
  this.name = name;
}
```
