# Redux in React

```jsx
import React from "react"
import ReactDOM from "react-dom"
import {Provider} from "react-redux"

import App from "./App"
import store from "./redux"

ReactDOM.render(
    <Provider store={store}>
        <App />
    </Provider>,
    document.getElementById("root")
)
```

## connect()

Documentation: https://react-redux.js.org/api/connect#connect

### How does `connect` work?

1. Higher-order component
2. Pass 2 things:
    1. What parts of the global state does the component want access to?
    2. What actions do you want to be able to dispatch from this component?
3. It thens returns a function to which you pass the component you want to connect. When called, this function creates a new component wrapping yours which passes the global state and "dispatchable" actions to your component via props.

```js
connect(mapStateToPropsFunc, mapDispatchToPropsFunc)(Component)
```

### Example

App.js

```jsx
import React from "react"
import {connect} from "react-redux"
import {increment, decrement} from "./redux"

function App(props) {
    return (
        <div>
            <h1>{props.count}</h1>
            <button onClick={props.decrement}>-</button>
            <button onClick={props.increment}>+</button>
        </div>
    )
}

const mapStateToProps = (globalState) => ({count: globalState})
const mapDispatchToProps = {increment, decrement}

export default connect(mapStateToProps, mapDispatchToProps)(App)
```

## Hooks

`useSelector()` & `useDispatch()`: replacement for the 2 params in `connect()`

App.js

```jsx
import React from "react"
import {useSelector, useDispatch} from "react-redux"
import {increment, decrement} from "./redux"

export default function App(props) {
    const count = useSelector(state => state)
    const dispatch = useDispatch()
    
    return (
        <div>
            <h1>{count}</h1>
            <button onClick={() => dispatch(decrement())}>-</button>
            <button onClick={() => dispatch(increment())}>+</button>
        </div>
    )
}
```

## Redux-Thunk

```js
import redux, {createStore, applyMiddleware} from "redux"
import thunk from "redux-thunk"

function reducer(state, action) { ... }

export function increment() {
    return (dispatch, getState) => {
        // do something with `dispatch()` and `getState()`
    }
}

const store = createStore(reducer, applyMiddleware(thunk))
```