## Title : Optimize Character Count

### Problem Statement

In a React application, you are tasked with building a component where a user can type comments into a textarea and submit them. The component should also display a count of the characters left, which is dynamically updated as the user types. However, the current implementation results in the entire component re-rendering whenever the user types a character, leading to performance issues, especially as the component complexity grows.

### Code Stub (Before Optimization)

```jsx
import React, { useState } from "react";

function CommentBox() {
  const [comment, setComment] = useState("");
  const maxLength = 200;

  const handleChange = (event) => {
    setComment(event.target.value);
  };

  return (
    <div>
      <textarea value={comment} onChange={handleChange} maxLength={maxLength} />
      <p>{maxLength - comment.length} characters left</p>
    </div>
  );
}

export default CommentBox;
```

### Problem and Optimization Task

Your task is to optimize the `CommentBox` component by using the `useRef` hook to track the number of characters left without causing re-renders for the whole component every time the user types. This approach ensures that updates to the character count are efficient and do not impact the performance of other parts of the component.

### Hints

1. Utilize `useRef` to create a reference for the textarea element.
2. Update the count of characters left by directly manipulating the DOM in the `handleChange` function, thereby avoiding state updates and re-renders.
3. Ensure the initial character count is displayed correctly when the component mounts.

### Optimized Solution

```jsx
import React, { useState, useRef, useEffect } from "react";

function CommentBox() {
  const [comment, setComment] = useState("");
  const maxLength = 200;
  const charCountRef = useRef(null);

  useEffect(() => {
    charCountRef.current.innerText = `${maxLength} characters left`;
  }, []); // Only on mount

  const handleChange = (event) => {
    setComment(event.target.value);
    charCountRef.current.innerText = `${
      maxLength - event.target.value.length
    } characters left`;
  };

  return (
    <div>
      <textarea value={comment} onChange={handleChange} maxLength={maxLength} />
      <p ref={charCountRef}></p>
    </div>
  );
}

export default CommentBox;
```

### Solution Approach

1. Import `useRef` from React.
2. Create a ref for the character count paragraph.
3. In the `handleChange`, update the inner text of this paragraph directly.
4. Set the initial text content of the character count paragraph in the useEffect to ensure it's correct on the first render.
