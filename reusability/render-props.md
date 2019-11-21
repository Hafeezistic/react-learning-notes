# Render Props

Could be used to separate interface and logic.

## Sample Code

App.js

```jsx
import React from "react"
import Example from "./Example"

export default function App () {
    return (
        <div>
            <Example render={
                isDaytime => (
                    <h1>{ isDaytime ? "Good day" : "Good evening" }, Alex!</h1>
                )
            }/>
        </div>
    )
}
```

Example.js

```jsx
import React from "react"

export default function Example(props) {
    return (
        <div>
            {props.render(true)}
        </div>
    )
}
```

## Refactor Higher-Order Components

Refactor previous sample code written in higher-order components with render props.

Toggler.js (previously `withToggler.js`)

```jsx
import React from "react"

export default class Toggler extends React.Component {
    this.state = {
        on: this.props.defaultOnValue
    }
    
    toggle = () => {
        this.setState(prevState => ({
            on: !prevState.on
        }))
    }
    
    render() {
        return (
            <div>
                {this.props.render(this.state.on, this.props.toggle)}
            </div>
        )
    }
}

Toggler.defaultProps = {
    defaultOnValue: false
}
```

Favorite.js

```jsx
import React from "react"
import Toggler from "./Toggler"

function Favorite(props) {
    return (
        <Toggler render={
            (on, toggle) => (
                <div>
                    <h3>Click heart to favorite</h3>
                    <h1>
                        <span 
                            onClick={toggle}
                        >
                            {on ? "❤️" : "♡"}
                        </span>
                    </h1>
                </div>
            )
        }/>
    )
}
```