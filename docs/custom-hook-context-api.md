# How to create your own custom hook for the context api

You can create your own custom hook for the code that initilizes the context api.

## Steps to create custom hook
1. Create a context using React.createContext() API

2. Create a functional component accepting 'children' as argument. This functional component will be your context provider.

3. Inside the return function of context provider, wrap all the children within the context.

4. Initialize the 'vaule' attribute of the context provider.

## Example code

```js
import React, { useContext, useState } from "react";

const ThemeContext = React.createContext();
const ThemeUpdateContext = React.createContext();

export function useTheme() {
  return useContext(ThemeContext);
}

export function useThemeUpdate() {
  return useContext(ThemeUpdateContext);
}

export function ThemeProvider({ children }) {
  const [darkTheme, setDarkTheme] = useState(true);

  function toggleTheme() {
    setDarkTheme((preDarkTheme) => !preDarkTheme);
  }
  return (
    <ThemeContext.Provider value={darkTheme}>
      <ThemeUpdateContext.Provider value={toggleTheme}>
        {children}
      </ThemeUpdateContext.Provider>
    </ThemeContext.Provider>
  );
}
```
## Explanation
1. The above code is creating two instances of context
    1. one for providing 'theme' value
    2. another one for providing a method to update the theme value.

2. Here two custom hooks are created 'useTheme' and 'useThemeUpdate'
    1. 'useTheme' hooks is calling 'useContext' react hook and passing the 'ThemeContext' as the argument and returning
    2. 'useThemeUpdate' hook is calling 'useContext' react hook and passing the 'ThemeUpdateContext' as the argument and returning

3. The functional component 'ThemeProvider' accepting 'children' as the argument and wrapping the 'children' within the
'ThemeContext.Provider' and 'ThemeUpdateContext.Provider'