# Shallow Comparison

## For primitive types

e.g. string, number, boolean
Check if they triple equal (`===`) each other, alway `true`.

```js
console.log("Hi" === "Hi") // true
```

## For complex types

e.g. object, array
Check if the first level of its children triple equal each other.

```js
console.log({name: "Joe"} === {name: "Joe"}) // false
```

