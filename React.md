# React Study Note

## Context
### Introduction
Context provides a way to pass data through the component tree without having to pass props down manually at every level.

### When to Use Context
Context is designed to share data that can be considered “global” for a tree of React components, such as the current authenticated user, theme, or preferred language.

### Context.Provider
* ***Deletemin change:*** All consumers that are descendants of a Provider will re-render whenever the Provider’s value prop changes.
* **Always render:** The propagation from Provider to its descendant consumers (including .contextType and useContext) is not subject to the shouldComponentUpdate method, so the consumer is updated even when an ancestor component skips an update.
* ***Compare algorithm:*** Changes are determined by comparing the new and old values using the same algorithm as [Object.is](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is#Description).

### Caveats
* ***resuse:*** Apply it sparingly because it makes component reuse more difficult.
* ***Performance:*** Because context uses reference identity to determine when to re-render, there are some gotchas that could trigger unintentional renders in consumers when a provider’s parent re-renders.
