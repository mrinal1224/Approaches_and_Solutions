**Problem Description**
Create a base class Vehicle with a method start that prints a message indicating the vehicle has started. Implement two subclasses, Car and Motorcycle, that extend the Vehicle class. Override the start method in each subclass to provide a customized message.

Test Cases

```javascript
const car = new Car();
car.start(); // Output: "Car started!"

const motorcycle = new Motorcycle();
motorcycle.start(); // Output: "Motorcycle started!"
```

**Hints**
Use the `super` keyword to call the start method of the parent class.

**Solution Approach**
Create a base class Vehicle with a start method that prints a message indicating the vehicle has started.
Create two subclasses, Car and Motorcycle, that extend the Vehicle class.
Override the start method in each subclass to provide a customized message.

**Solution**

```javascript
class Vehicle {
  start() {
    console.log("Vehicle started!");
  }
}

class Car extends Vehicle {
  start() {
    console.log("Car started!");
  }
}

class Motorcycle extends Vehicle {
  start() {
    console.log("Motorcycle started!");
  }
}
```
