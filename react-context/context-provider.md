# Context Provider

```js
const ThemeContext = React.createContext()
// ThemeContext.Provider & ThemeContext.Consumer

const {Provider, Consumer} = ThemeContext // Optional destructuring assignment

ReactDOM.render(
    <Provider value={"light"}>
        <App />
    </Provider>,
    document.getElementById("root")
)
```

⚠️ In actual development, move the context to a dedicated file to avoid polluting `index.js` or causing a bug.

themeContext.js

```js
import React from "react"
const ThemeContext = React.createContext()
export default ThemeContext
```