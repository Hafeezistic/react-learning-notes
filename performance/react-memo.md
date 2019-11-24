# React.memo()

- Higher-order component built by React
- Pretty much the same as `PureComponent`, but for functional components
- It only compares prevProps and nextProps (no state checking)
- You can optionally implement your own checking function to determine if it should use the memorized result
    - This function is kind of like `shouldComponentUpdate()`, except it should return `true` if the props are equal and `false` if they aren't. This is effectively the opposite approach of `shouldComponentUpdate()`, which returns `true` if the component should re-render (i.e. props are different).

| | shouldComponentUpdate() | React.memo() |
|---|---|---|
| Should re-render (props changed) | `true` | `false` |
| Should not re-render (props are equal) | `false` | `true` |

## Usage

```jsx
export default React.memo(Component[, areEqual])
```

The component will be cached and used to check props changes. 

Default `areEqual()` in React: `React.areEqual()`. You can use the following format to implement a custom version of `areEqual()` and pass it as the second parameter in `React.memo()`:

```js
function areEqual(prevProps, nextProps) {
    /*
    return true if passing nextProps to render would return
    the same result as passing prevProps to render,
    otherwise return false
    */
}
```
