# contextType

Example.js

```jsx
import React, {Component} from "react"
import ExampleContext from "./exampleContext"

export default class Example extends Component {
    console.log(this.context) // the value passed by the context type
    render() {
        return (
            <button className="light-theme">Switch Theme</button>
        )
    }
}

Button.contextType = ExampleContext
```

⚠️ Only works in class component.