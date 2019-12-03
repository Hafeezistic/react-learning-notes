# useParams

```jsx
<Switch>
    <Route path="/services/:id"> {/* route param */}
        <ServiceDetail />
    </Route>
</Switch>
```

ServiceDetail.js

```jsx
import React from "react"
import {useParams} from "react-router-dom"

export default function ServiceDetail() {
    const {id} = useParams()
    // AJAX get service detail by `id`
    // Simulating:
    const thisService = servicesList.find(i => i._id === id)
    return (
        <div>
            <h1>{thisService.title}</h1>
            <p>{thisService.description}</p>
        </div>
    )
}
```