# Switch and Route

## Method #1: Using `render` prop

Useful when you want to pass props to the component you want to render

```jsx
import React from "react"
import {Link, Switch, Route} from "react-router-dom"

import Home from "./Home"
import About from "./About"

function App() {    
    return (
        <div>
            <Link to="/">Home</Link>
            <Link to="/about">About</Link>
            
            <Switch>
                <Route exact path="/" render={() => <Home />} />
                <Route path="/about" render={() => <About />} />
            </Switch>
        </div>
    )
}

export default App
```

## Method #2: Using `component` prop

```jsx
import React from "react"
import {Link, Switch, Route} from "react-router-dom"

import Home from "./Home"
import About from "./About"

function App() {    
    return (
        <div>
            <Link to="/">Home</Link>
            <Link to="/about">About</Link>
            
            <Switch>
                <Route exact path="/" component={Home} />
                <Route path="/about" component={About} />
            </Switch>
        </div>
    )
}

export default App
```

## Method #3: Using children

Latest and recommended

```jsx
import React from "react"
import {Link, Switch, Route} from "react-router-dom"

import Home from "./Home"
import About from "./About"

function App() {    
    return (
        <div>
            <Link to="/">Home</Link>
            <Link to="/about">About</Link>
            
            <Switch>
                <Route exact path="/"><Home /></Route>
                <Route path="/about"><About /></Route>
            </Switch>
        </div>
    )
}

export default App
```