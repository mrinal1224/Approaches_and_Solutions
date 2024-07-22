**Raw Problem**
You are building a simple banking system. Implement a BankAccount class with private properties accountNumber and balance. Create methods for deposit and withdraw that modify the balance property accordingly.

**Problem Description:**
Create a class BankAccount with private properties accountNumber and balance. The accountNumber should be generated automatically when a new account is created.
Implement a private method generateAccountNumber to generate a unique account number for each account.
Implement public methods deposit and withdraw that allow users to modify the balance property. Ensure that withdrawals cannot result in a negative balance. return 'Insufficient funds' in such cases.

Please make sure the below test cases are fulfilled:

```javascript
const account = new BankAccount();
console.log(account.deposit(1000)); // Output: 1000
console.log(account.withdraw(500)); // Output: 500
console.log(account.withdraw(1000)); // Output: "Insufficient funds"
```

**Hints**
Use the `#` symbol to declare private properties in a class.
Use the `this` keyword to access properties and methods within the class.
Use the `Math.random()` method to generate a random number for the account number.

**Solution Approach**
Create a class BankAccount with private properties accountNumber and balance.
Implement a private method generateAccountNumber to generate a unique account number for each account.
Implement public methods deposit and withdraw that allow users to modify the balance property. Ensure that withdrawals cannot result in a negative balance.

**Solution**

```javascript
class BankAccount {
  #accountNumber;
  #balance;

  constructor() {
    this.#accountNumber = this.generateAccountNumber();
    this.#balance = 0;
  }

  generateAccountNumber() {
    return Math.floor(Math.random() * 1000000000);
  }

  deposit(amount) {
    this.#balance += amount;
    return this.#balance;
  }

  withdraw(amount) {
    if (this.#balance - amount < 0) {
      return "Insufficient funds";
    }
    this.#balance -= amount;
    return this.#balance;
  }
}
```
