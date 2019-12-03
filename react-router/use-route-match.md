# useRouteMatch

Documentation: https://reacttraining.com/blog/react-router-v5-1/#useroutematchf

```jsx
import React from "react"
import {Link, Route, Switch, useRouteMatch} from "react-router-dom"

// components
import Settings from "./Settings"
import Info from "./Info"

function Profile() {
    const {path, url} = useRouteMatch()
    
    return (
        <div>
            <h1>Profile Page</h1>
            <ul>
                <li><Link to={`${url}/info`}>Profile Info</Link></li>
                <li><Link to={`${url}/settings`}>Profile Settings</Link></li>
            </ul>
            
            <Switch>
                <Route path={`${path}/info`}>
                    <Info/>
                </Route>
                <Route path={`${path}/settings`}>
                    <Settings/>
                </Route>
            </Switch>
        </div>
    )
}
```