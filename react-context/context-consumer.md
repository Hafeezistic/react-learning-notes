# Context Consumer

In functional components, we cannot use the static `contextType` property. Instead, we can use the context consumer to help get the value of a certain context.

```jsx
import React from "react"
import ExampleContext from "exampleContext"

export default function Example(props) {
    return (
        <ExampleContext.Consumer>
            { example => (
                <div>Display: {example}</div>
            ) }
        </ExampleContext.Consumer>
    )
}
```