# Introduction

In React, you can only pass data downwards. -> Prop drilling

> Context provides a way to pass data through the component tree without having to pass props down manually at every level. 
> 
> React Docs
> https://reactjs.org/docs/context.html

`Provider` provides `Consumer`s with the global data they need along with a function to modify that data.

## Caveats

- Don't use context just to avoid prop drilling a layer or two down (React: [Before you use Context](https://reactjs.org/docs/context.html#before-you-use-context))
- Don't use context for state that should just be kept locally (e.g. forms)
- Wrap the Provider around the lowest common parent in the tree
- Passing object as value, watch performance and refactor if necessary