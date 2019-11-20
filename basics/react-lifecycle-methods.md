# React Lifecycle Methods

## Links
[React Lifecycle Methods- how and when to use them - Code == Life](https://engineering.musefind.com/react-lifecycle-methods-how-and-when-to-use-them-2111a1b692b1)
https://reactjs.org/blog/2018/03/29/react-v-16-3.html#component-lifecycle-changes

## `render()`

Everybody knows

## `componentDidMount()`

Only run once before the component is displayed to the screen
e.g. API calls

## `componentDidUpdate(prevProps, prevState)`

Using `this.setState()` inside the method unconditionally will cause **infinite loop** error

## *DEPRECATED* `componentWillReceiveProps(nextProps)`

Run every time the component receives props from the parent component
e.g. check if the props changed 

## `shouldComponentUpdate(nextProps, nextState)`

Return `true` if want it to update.
Return `false` if not.

## `componentWillUnmount()`

Teardown or cleanup your code before your component disappears
e.g. remove event listener

## `static getDerivedStateFromProps(props, state)`

Return new, updated state based upon the props.
[You Probably Don’t Need Derived State – React Blog](https://reactjs.org/blog/2018/06/07/you-probably-dont-need-derived-state.html)
[React.Component – React](https://reactjs.org/docs/react-component.html#static-getderivedstatefromprops)

## `getSnapshotBeforeUpdate()`

Create a backup of the current way things are.
Not a common React lifecycle methods.
[React.Component – React](https://reactjs.org/docs/react-component.html#getsnapshotbeforeupdate)

