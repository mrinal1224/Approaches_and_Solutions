**Problem Description**
You are given an object car with properties make and engine.
You need to complete the engine property such that.
The engine property should be another object with a method start that logs "Car started: [make]". Use the this keyword to access the make property.

Test Case:

```js
const car = {
    make: "Toyota",
    engine: // Write code here
  };

car.engine.start();  // Output: 'Car started: Toyota'
```

**Hints**

- Use the this keyword to access the make property inside the start method.

**Solution**

```js
const car = {
  make: "Toyota",
  engine: {
    start: function () {
      console.log(`Car started: ${this.make}`);
    },
  },
};
```
