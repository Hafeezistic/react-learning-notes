# React Hooks

## `useState()`

## `useEffect()`

### Replace `componentDidUpdate()`
Watch the updates of only a list of state(s) provided
```js
useEffect(() => {
	// do something
}, []) // when the state(s) in the array of the 2nd parameter changes
```

### Replace `componentDidMount()`
```js
useEffect(() => {
	// code
}, []) // include nothing in the second parameter
```

### Replace `componentWillUnmount()`
Return a function that runs when the component unmount 
(to, e.g., clean up)
```js
useEffect({
	// e.g. set up a event listener
	return () => {
		// e.g. clean up the event listener set up before
	}
}, [])
```
