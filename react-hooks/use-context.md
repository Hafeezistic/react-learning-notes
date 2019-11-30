# useContext()

themeContext.js

```jsx
import React, {useState, createContext} from "react"

const ThemeContext = createContext()

function ThemeContextProvider(props) {
    const theme = useState(false)
    
    toggleTheme = () => {
        setTheme(p => !p)
    }
    
    return (
        <ThemeContext.Provider value={{
            theme: (theme ? "light" : "dark"),
            toggleTheme
        }}>
            {props.children}
        </ThemeContext.Provider>
    )
}

export {ThemeContextProvider, ThemeContext}
```

index.js

```jsx
import React from "react"
import ReactDOM from "react-dom"

import App from "./App"
import {ThemeContextProvider} from "./themeContext"

ReactDOM.render(
    <ThemeContextProvider>
        <App />
    </ThemeContextProvider>, 
    document.getElementById("root")
)
```

Some component that uses that context: **e.g.** `Button.js`

```js
import React, {useContext} from "react"
import {ThemeContext} from "./themeContext"

function Button(props) {
    const {theme, toggleTheme} = useContext(ThemeContext)
    return (
        <button 
            onClick={toggleTheme} 
            className={`${theme}-theme`}
        >
            Switch Theme
        </button>
    )    
}

export default Button
```