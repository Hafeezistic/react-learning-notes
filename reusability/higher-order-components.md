# Higher-order Components

- stems from the concept of **higher-order functions**
- **Definition:** a function that takes a component as its first argument and returns a new component that wraps the given component, providing extra capabilities to it

```jsx
const upgradeComponent = withSuperPowers(Component)
export default upgradeComponent
```

### Example:

```jsx
const componentWithToggle = withToggle(Component)
export default componentWithToggle
```

usual form:

```jsx
export default withToggle(Component)
```

## How to write

```jsx
function withSuperPower(component) {
    const Component = component // just a convention
    return function (props) {
        return (
            <Component superPower="now you got super powers" {...props} />
        )
    }
}
```

## Sample Code

withToggler.js

```jsx
import React from "react"

class Togger extends React.Component {
    state = {
        on: this.props.defaultOnValue
    }
    
    toggle = () => {
        this.setState(prevState => ({
            on: !prevState.on
        }))
    }
    
    render() {
        const {component: Component, defaultOnValue, ...props} = this.props
        return (
            <Component on={this.state.on} toggle={this.toggle} {...props} />
        )
    }
}

export function withToggler(component, optionsObj) {
    return function (props) {
        return (
            <Toggler component={component} defaultOnValue={optionsObj.defaultOnValue} {...props} />
        )
    }
}
```

Favorite.js

```jsx
import React from "react"
import {withToggler} from "./HOCs/withToggler.js"

function Favorite(props) {
    return (
        <div>
            <h3>Click heart to favorite</h3>
            <h1>
                <span 
                    onClick={props.toggle}
                >
                    {props.on ? "❤️" : "♡"}
                </span>
            </h1>
        </div>
    )
}

export default withToggler(Favorite)
```

Higher-order functions could potentially be replaced by React Hooks, but are still useful when looking through legacy codes.

