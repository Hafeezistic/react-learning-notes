# Introduction

Single-Page Application (SPA) -> **Conditional Rendering** in React

# Simplified Model

```jsx
import React, {useState} from "react"

function App() {
    const [page, setPage] = useState("home")
    
    return (
        <div>
            <nav>
                <button onClick={() => setPage("home")}>Home</button>
                <button onClick={() => setPage("contact")}>Contact</button>
                <button onClick={() => setPage("about")}>About</button>
            </nav>
            {
                page === "home" ? <h1>Home Page</h1> : 
                page === "contact" ? <h1>Contact Page</h1> :
                page === "about" ? <h1>About Page</h1> :
                <h1>Error!</h1>
            }
        </div>
    )
}
```

## React Router

- Conditionally render large parts of your page
- Declarative API
- Hooks

### Primary Component

- Routers
    - `<BrowserRouter>`
    - `<HashRouter>`
- Route Matchers
    - `<Route>`
    - `<Switch>`
- Navigation ("route changers")
    - `<Link>`
    - `<NavLink>`
    - `<Redirect>`

### Hooks

- useHistory
- useLocation
- useParams