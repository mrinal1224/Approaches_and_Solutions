### Problem Statement

**Title:** Optimizing User Settings Management with React Context API

**Description:**
You are tasked with refactoring an existing React application that manages user settings across multiple components. Currently, the application uses prop drilling to pass user preferences (like theme and language) down through several levels of components, making the code difficult to manage and scale.

Your goal is to optimize the codebase by implementing the React Context API to provide a more efficient and maintainable way to access user settings across the application. You will need to create a `SettingsContext` to handle the theme and language preferences, eliminating the need for prop drilling.

**Initial Code Setup (with Prop Drilling):**

```jsx
// App.js
import React from 'react';
import UserSettings from './UserSettings';
import Profile from './Profile';

function App() {
  const [theme, setTheme] = React.useState('light');
  const [language, setLanguage] = React.useState('English');

  return (
    <div>
      <UserSettings theme={theme} setTheme={setTheme} language={language} setLanguage={setLanguage} />
      <Profile theme={theme} language={language} />
    </div>
  );
}

export default App;

// UserSettings.js
import React from 'react';

function UserSettings({ theme, setTheme, language, setLanguage }) {
  return (
    <div>
      <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
        Toggle Theme
      </button>
      <button onClick={() => setLanguage(language === 'English' ? 'Spanish' : 'English')}>
        Toggle Language
      </button>
    </div>
  );
}

export default UserSettings;

// Profile.js
import React from 'react';

function Profile({ theme, language }) {
  return (
    <div style={{ color: theme === 'light' ? 'black' : 'white' }}>
      Profile Page in {language}
    </div>
  );
}

export default Profile;
```

**Requirements:**

1. Refactor the above code to use React Context API.
2. Ensure that the `Profile` and `UserSettings` components consume context instead of props for theme and language settings.
3. The application's functionality (theme and language toggling) must remain unchanged.

**Hints:**

- Initialize a `SettingsContext` using React's `createContext`.
- Provide the `SettingsContext` at the top level in `App.js`.
- Use the `useContext` hook in `UserSettings.js` and `Profile.js` to consume the context.

### Solution Approach

1. **Create Context:**

   - Define `SettingsContext` and an associated provider in a new file or at the top of `App.js`.
   - The provider should wrap all components that require access to the settings.

2. **Consuming Context:**

   - Modify `UserSettings` and `Profile` to use the `useContext` hook to access theme and language settings from `SettingsContext`.

3. **Testing:**
   - Write test cases to ensure that toggling theme and language updates the UI accordingly. Utilize libraries like Jest and React Testing Library.

### Complete Solution

**SettingsContext.js:**

```jsx
import React from "react";

export const SettingsContext = React.createContext();

export const SettingsProvider = ({ children }) => {
  const [theme, setTheme] = React.useState("light");
  const [language, setLanguage] = React.useState("English");

  const toggleTheme = () => setTheme(theme === "light" ? "dark" : "light");
  const toggleLanguage = () =>
    setLanguage(language === "English" ? "Spanish" : "English");

  return (
    <SettingsContext.Provider
      value={{
        theme,
        setTheme: toggleTheme,
        language,
        setLanguage: toggleLanguage,
      }}
    >
      {children}
    </SettingsContext.Provider>
  );
};
```

**App.js:**

```jsx
import React from "react";
import { SettingsProvider } from "./SettingsContext";
import UserSettings from "./UserSettings";
import Profile from "./Profile";

function App() {
  return (
    <SettingsProvider>
      <UserSettings />
      <Profile />
    </SettingsProvider>
  );
}

export default App;
```

**UserSettings.js and Profile.js are updated similarly by consuming context using `useContext`.**

## Solution Approach

### Create Context

- **SettingsContext Initialization**: A new context, `SettingsContext`, is created to encapsulate the user settings. This context centralizes the management of theme and language preferences, which were previously managed and passed down manually through props.

- **Provider Implementation**: The `SettingsProvider` component is introduced. It houses the state management logic for theme and language settings using React's `useState`. This provider component will wrap the root component or the component tree that requires access to these settings, thereby making them globally accessible to any nested component within its wrapper.

### Implement Provider

- **State Management**: Inside the `SettingsProvider`, functions to toggle the theme (`toggleTheme`) and language (`toggleLanguage`) are implemented. These functions update the respective states based on user interaction.

- **Context Provision**: The `SettingsProvider` renders a `SettingsContext.Provider` element, passing down the current theme and language settings, along with the toggle functions as context values. This setup ensures that any component within the provider's scope can access and modify the settings without requiring them to be passed explicitly as props.

### Consuming Context

- **Refactor Components**: Components such as `UserSettings` and `Profile` are updated to consume the `SettingsContext` using the `useContext` hook. By consuming the context, these components gain direct access to the theme and language settings and the functions to modify them.

- **Simplification of Component Props**: With the context in place, there is no longer a need to pass theme and language settings through component props, significantly simplifying the component structure and improving maintainability.
