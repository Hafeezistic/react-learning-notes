# shouldComponentUpdate()

- Lifecycle method on class components
- Allows you to determine if a component should update or not
- Receives the upcoming props and state so you can compare them against current props and state
- `return true` for "yes", `return false` for "no"
- Don't deep equality checks here (recommended by React)
- Not really needed to be implemented by yourself

```jsx
shouldComponentUpdate(nextProps, nextState) {
     // code here
}
```