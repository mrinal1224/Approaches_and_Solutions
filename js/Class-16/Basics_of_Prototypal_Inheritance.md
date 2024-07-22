**Problem Description**
Create a simple JavaScript program to demonstrate prototypal inheritance.
Define a constructor function Person that takes a name as a parameter and sets it as an instance property. Then, create two instances of Person and add a method to the prototype that allows each person to introduce themselves.

Test Cases:

```javascript
// Constructor function for Person
function Person(name) {
  this.name = name;
}

// Create person instances
const person1 = new Person("John");
const person2 = new Person("Jane");

// Test cases
console.log(person1.introduce()); // Output: Hi, I'm John.
console.log(person2.introduce()); // Output: Hi, I'm Jane.
```

**Hints**

- Use the `this` keyword to set instance properties in the constructor function.
- Use the `prototype` property to add methods that can be shared across instances.

**Solution Approach**

- Define a constructor function Person that takes a name as a parameter and sets it as an instance property.
- Create two instances of Person using the `new` keyword.
- Add a method to the prototype of Person that allows each person to introduce themselves.

**Solution**

```javascript
// Constructor function for Person
function Person(name) {
  this.name = name;
}

// Add introduce method to the prototype
Person.prototype.introduce = function () {
  return `Hi, I'm ${this.name}.`;
};

// Create person instances
const person1 = new Person("John");
const person2 = new Person("Jane");

// Test cases
console.log(person1.introduce()); // Output: Hi, I'm John.
console.log(person2.introduce()); // Output: Hi, I'm Jane.
```
