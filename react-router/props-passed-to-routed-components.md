# Props passed to routed components

Sample props passed by React Router to routed component

```js
{
    history: {
        length: 32, 
        action: "POP", 
        location: {
            pathname: "/", 
            search: "", 
            hash: "", 
            state: null
        }, 
        createHref: createHref(location), 
        push: push(path, state), 
        replace: replace(path, state), 
        go: go(n), 
        goBack: goBack(), 
        goForward: goForward(), 
        block: block(prompt), 
        listen: listen(listener)
    }, 
    location: {
        pathname: "/", 
        search: "", 
        hash: "", 
        state: null
    }, 
    match: {
        path: "/", 
        url: "/", 
        isExact: true, 
        params: {}
    }, 
    staticContext: null
}
```
## Method #1

```jsx
<Route exact path="/" render={props => {
    console.log(props) // props passed by React Router
    return <Home />
}} />
```

## Method #2

```jsx
<Route exact path="/" component={Home} />
...
function Home(props) {
    console.log(props) // props passed by React Router
    return <h1>Home</h1>
}
```

## Method #3

```jsx
<Route exact path="/">
    <Home />
</Route>
```

Cannot directly access the props passed by React Router, use Hooks!

```jsx
import React from "react"
import {useLocation, useParams, useHistory, useRouteMatch} from "react-router-dom"
```
