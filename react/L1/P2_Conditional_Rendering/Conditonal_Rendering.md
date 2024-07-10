# Conditional Rendering

## Problem Statement : Create parent components

`Note` : these questions will do string matching and to avoid confusion please write the exact text

- You are given Packing List component

```jsx
export default function PackingList() {
  return (
    <section>
      <h1>Sally Ride's Packing List</h1>
      <ul>
        <Item isPacked={true} name="Space suit" />
        <Item isPacked={true} name="Helmet with a golden leaf" />
        <Item isPacked={false} name="Photo of Tam" />
      </ul>
    </section>
  );
}
```

- Your Task is to create -> Item component that
  - accepts two props `name` and `isPacked`.
  - It should render -> name and if ispacked is true then print : "'✔'" and ❌ if false

## Complete Solution

```jsx
function Item({ name, isPacked }) {
  return (
    <li className="item">
      {name} {isPacked ? "✔" : "❌"}
    </li>
  );
}

export default function PackingList() {
  return (
    <section>
      <h1>Sally Ride's Packing List</h1>
      <ul>
        <Item isPacked={true} name="Space suit" />
        <Item isPacked={true} name="Helmet with a golden leaf" />
        <Item isPacked={false} name="Photo of Tam" />
      </ul>
    </section>
  );
}
```
