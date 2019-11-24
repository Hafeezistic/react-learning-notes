# React.PureComponent

- Alternative to `React.Component`
- Automatically implements `shouldComponentUpdate()` for shallow props and state comparisons
- Disallow using `shouldComponentUpdate()` manually
- Skip rendering all children in the tree automatically, so they must be "pure" as well
- Generally preferred over `shouldComponentUpdate()`

Premature optimization