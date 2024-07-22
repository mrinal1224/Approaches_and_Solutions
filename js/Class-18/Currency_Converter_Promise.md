**Problem Description**
Write a function convertCurrency that takes an amount, source currency, and target currency, and returns a Promise. The Promise should resolve with the converted amount if the conversion is successful; otherwise, it should reject with an error message.

You need to implement the convertCurrency function, which returns a Promise. The Promise should resolve with the converted amount if the conversion is successful, and reject with an error message if there is any issue.

```javascript
// Test Cases
convertCurrency(100, "USD", "EUR")
  .then((result) => console.log(`Converted amount: ${result} EUR`))
  .catch((error) => console.error(error));

convertCurrency(50, "USD", "JPY")
  .then((result) => console.log(`Converted amount: ${result} JPY`))
  .catch((error) => console.error(error)); // Expected output: "Error converting currency: Invalid currency"
```

**Solution**

```javascript
function convertCurrency(amount, sourceCurrency, targetCurrency) {
  const exchangeRates = {
    USD: { EUR: 0.85, JPY: 110.0 },
    EUR: { USD: 1.18, JPY: 129.41 },
    JPY: { USD: 0.0091, EUR: 0.0077 },
  };

  return new Promise((resolve, reject) => {
    if (
      exchangeRates[sourceCurrency] &&
      exchangeRates[sourceCurrency][targetCurrency]
    ) {
      const convertedAmount =
        amount * exchangeRates[sourceCurrency][targetCurrency];
      resolve(convertedAmount);
    } else {
      reject("Error converting currency: Invalid currency");
    }
  });
}
```
