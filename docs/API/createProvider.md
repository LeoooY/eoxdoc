---
id: createProvider
title: createProvider
sidebar_label: createProvider
---

## API

``` javascript
createProvider(reducers, initState);
```

## Example

``` javascript
const initState = 0
const reducer = (state, action) => {
        const { type, data } = action
        switch (type) {
            case 'add':
                return state+1;
            default:
                return state;
        }
const { Provider, Context } = createProvider(reducers, initState);
```

* `Context` is created by `React.createContext()` inside the createProvider.

* `Provider` is the `Context.Provider` and  it has binded `state` and `dispatch` created by `useReducer(reducers, initState)` . 
