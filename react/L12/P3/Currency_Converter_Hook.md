## Title: Currency Converter Hook

### Problem Statement: Currency Converter Hook

Create a custom React hook called `useCurrencyConverter` that converts an amount from one currency to another using static exchange rates. This hook will facilitate currency conversions within components where such functionality is required.

#### Requirements:

1. The hook should accept two parameters:
   - `baseCurrency`: The currency from which the conversion should start.
   - `targetCurrency`: The currency to which the amount will be converted.
2. The hook should return a function:
   - `convert(amount)`: Takes a numerical value (the amount in `baseCurrency`) and returns the converted amount in `targetCurrency`.
3. Use the following predefined exchange rates for conversion:
   - USD to EUR: 0.93
   - EUR to USD: 1.07
   - GBP to USD: 1.21
4. If an unsupported currency pair is used or if the input amount is not a number, the `convert` function should return `null`.

#### Code Stub

```jsx
import { useCallback } from "react";

function useCurrencyConverter(baseCurrency, targetCurrency) {
  const convert = useCallback(
    (amount) => {
      // Conversion logic will be placed here.
    },
    [baseCurrency, targetCurrency]
  );

  return convert;
}

export default useCurrencyConverter;
```

#### Simplified Solution

For a straightforward approach, we can use a series of `if` statements to determine the conversion based on the currency pair:

```jsx
import { useCallback } from "react";

function useCurrencyConverter(baseCurrency, targetCurrency) {
  const convert = useCallback(
    (amount) => {
      if (isNaN(amount)) {
        return null; // Return null if the amount is not a number
      }

      if (baseCurrency === "USD" && targetCurrency === "EUR") {
        return amount * 0.93;
      } else if (baseCurrency === "EUR" && targetCurrency === "USD") {
        return amount * 1.07;
      } else if (baseCurrency === "GBP" && targetCurrency === "USD") {
        return amount * 1.21;
      } else {
        return null; // Return null for unsupported currency pairs
      }
    },
    [baseCurrency, targetCurrency]
  );

  return convert;
}

export default useCurrencyConverter;
```

## Solution Approach

1. **Define the Hook**:

   - Use the `useCallback` hook to define the `convert` function within `useCurrencyConverter`.
   - The `convert` function will calculate the converted amount or return `null` for unsupported conversions.

2. **Implement Conversion Logic**:

   - Inside `convert`, use conditional statements to apply the appropriate conversion rate based on `baseCurrency` and `targetCurrency`.
   - Return `null` for unsupported currency pairs or non-numeric amounts.

3. **Optimize with useCallback**:
   - The `convert` function is memoized using `useCallback` with `baseCurrency` and `targetCurrency` as dependencies. This ensures that the function is only re-created when either currency changes, optimizing performance.
