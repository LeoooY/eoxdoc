---
id: withContext
title: withContext
sidebar_label: withContext
---

## API
``` javascript
withContext(Components, Context, ContextSelector)
```

## Example:
``` javascript
withContext(ChildComponents,Context,{
    dispatch: ctx => ctx.dispatch,
    state: ctx => ctx.state,
})
```
`withContext` links the context to ChildComponents. `ContextSelector` is similar to `Redux-mapStateToProps`