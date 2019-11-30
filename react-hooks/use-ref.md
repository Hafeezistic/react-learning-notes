# useRef()

```jsx
import React, { useEffect, useRef } from "react"

function App(props) {
    const inputRef = useRef(null) 
    // the passed parameter will be `inputRef.current`
    
    function onButtonClick() {
        inputRef.current.focus()
    }
    
    return (
        <input ref={inputRef} type="text" />
        <button onClick={onButtonClick}>Focus the input</button>
    )
}
```