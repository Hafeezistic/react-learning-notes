# useState()

## Creating state

App.js
```jsx
import React, {useState} from "react"

function App() {
    const [ value ] = useState(0) // ["Yes", f()]
    
    return (
        <div>
            <h1>Is state important to know? {value}</h1>
        </div>
    )
}
```

## Changing State

App.js
```jsx
import React, {useState} from "react"

function App() {
    const [ count, setCount ] = useState(0) // [0, f()]
    
    const increment = () => {
        setCount(prevCount => prevCount + 1)
    }
    
    return (
        <div>
            <h1>{count}</h1>
            <button onClick={increment}>plus 1</button>
        </div>
    )
}
```
