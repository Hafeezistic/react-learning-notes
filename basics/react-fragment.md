# React Fragment

```jsx
return (
    <React.Fragment>
        <Child />
        <AnotherChild />
    </React.Fragment>
)
```

You don't have to use `<div>` to wrap multiple elements up any more! That will cause unnecessary DOM pollution.

## Drawback

The parent-child relationship is lost. The fragments wrapped in another element become the siblings of that element after rendering.

## Shorthand

### Method 1
```jsx
return (
    <>
        <Child />
        <AnotherChild />
    </>
)
```

### Method 2

```jsx
import React, {Fragment} from "react"
return (
    <Fragment>
        <Child />
        <AnotherChild />
    </Fragment>
)
```