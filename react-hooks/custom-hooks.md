# Custom Hooks

A type of pattern that enables us to reuse our code. 

## Steps

1. initialize state
2. create any functions we need for modifying the state
3. return whatever we want another component to have access to

## Example

useCounter.js

```js
import {useState} from "react"

export default function useState() {
    const [count, setCount] = useState(0)
    function increment() {
        setCount(p => p + 1)
    }
    return [count, increment]
}
```

use it in `App.js`

```jsx
import React from "react"
import useCounter from "./useCounter.js"

export default function App() {
    const [num, add] = useCounter()
    
    return (
        <div>
            <h1>The count is {number}</h1>
            <button onClick={add}>Add 1</button>
        </div>
    )
}
```