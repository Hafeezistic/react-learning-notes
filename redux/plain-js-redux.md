# Plain JS Redux

Core philosophy of Redux

## Actions

```js
const redux = require("redux")

const action = {
    type: "ADD_ONE" // UPPER_SNAKE_CASE
}
```

### Action creator

```js
function increment() {
    return {
        type: "INCREMENT"
    }
}
```

### Payload in action creators

```js
function increment(amount) {
    return {
        type: "INCREMENT",
        payload: amount
    }
}

function reducer(state, action) {
    switch (action.type) {
        case "INCREMENT":
            return {
                count: state.count + action.payload
            }
        ...
    }
}
```

## Reducer

```js
function reducer(state = {count: 0}, action) {
    // return new state based on the incoming `action.type`
    switch (action.type) {
        case "INCREMENT":
            return {
                count: count + 1
            }
        case "DECREMENT":
            return {
                count: count - 1
            }
        default:
            return state
    }
}
```

## Store

### Create the Store

```js
const redux = require("redux")

function reducer(state, action) { ... }

const store = redux.createStore(reducer)
// pass the reducer function as param

console.log(store)
// {
//     dispatch: dispatch(action), 
//     subscribe: subscribe(listener),
//     getState: getState(),
//     replaceReducer: replaceReducer(nextReducer)
// }
```

### Set up subscribe function

```js
store.subscribe(() => {
    // run the function when state changes
    // e.g.
    doSomething(store.getState())
})
```

## dispatch

```js
store.dispatch({type: "INCREMENT"})
// equals to
store.dispatch(increment())
```

## combineReducers

 ```js
 const redux = require("redux")
 const {combineReducers, createStore} = redux
 
 import countReducer from "./count"
 import favoriteThingsReducer from "./favoriteThings"
 import youTubeVideoReducer from "./youTubeVideo"
 
 const rootReducer = combineReducers({
    count: countReducer,
    favoriteThings: favoriteThingsReducer,
    youTubeVideo: youTubeVideoReducer
})

export default createStore(rootReducer)
 ```