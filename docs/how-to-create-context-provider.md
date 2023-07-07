## Context API

React Context APIs are one of the ways to manage application state globally

1. How to create a context

```js
const applicationContext = React.createContext();
```

2. Using context APIs, we can pass down the values to all the componets of an application.
3. Create a context provider and wrap all the application components within that provider

```js
    // ApplicationContextProvider.js
    import React from 'react';
    export const ApplicationContextProvider = React.createContext();


    //App.js
    import { ApplicationContextProvider } from './ApplicationContextProvider';
    
    export default function App() {
        const theme = 'dark';
        return(
            <ApplicatoinContextProvider value = {theme}>
                // all application components go here
            </ApplicatoinContextProvider>
        )     
    }
```