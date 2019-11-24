# Move Context Provider to its own component

add state to context provider so we change context.

exampleContext.js

```jsx
import React,  {Component} from "react"

const {Provider, Consumer} = React.createContext()

class ExampleContextProvider extends Component {
    state = {
        value: true
    }
    
    toggle = () => {
        this.setState(prevState => ({
            value: !prevState.value
        }))
    }

    render() {
        return (
            <Provider value={{
                value: this.state.value,
                toggle: this.toggle
            }}>
                {this.props.children}
            </Provider>
        }
    }
}

export {ExampleContextProvider, Consumer as ExampleContextConsumer}
```

ExampleComponent.js

```jsx
import React from "react"
import {ExampleContextConsumer} from "./exampleContext"

export default function ExampleComponent(props) {
    return (
        <ThemeContextConsumer>
            {ctx => (
                <div>
                    value: {ctx.value}
                    <button onClick={ctx.toggle}>flip value</button>
                </div>
            )}
        </ThemeContextConsumer>
    )
}
```