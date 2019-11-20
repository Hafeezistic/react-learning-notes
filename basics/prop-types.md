# Prop Types

React dropped the ability to validate prop types and moved it to a dedicated library -- `prop-types`.

```jsx
import PropTypes from "prop-types"

Card.propTypes = {
    color: PropTypes.string.isRequired,
    height: PropTypes.number.isRequired,
    width: PropTypes.number
}
```

React docs: https://reactjs.org/docs/typechecking-with-proptypes.html#proptypes

Enum:

```jsx
Card.propTypes = {
    color: PropTypes.oneOf(["red", "blue"]).isRequired
}
```

Consider TypeScript!
