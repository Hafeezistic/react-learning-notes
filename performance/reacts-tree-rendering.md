# React's Tree Rendering

- React recursively renders components down one branch until there are no more to render
- Changes to state or props in any component will recursively re-render down the remaining tree whether those components have changed or not
    - This can cause significant performance problems
    - `shouldComponentUpdate()`, `React.PureComponent` and `React.memo()` are tools to help fix the problems