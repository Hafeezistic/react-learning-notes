# React Children

App.js
```jsx
import Example from "./Example"

function App() {
    return (
        <Example>
            <h1>Hello World</h1>
        </Example>
    )
}
```

Example.js
```jsx
function Example(props) {
    return (
        <div>
            {props.children}
        </div>
    )
}
```

