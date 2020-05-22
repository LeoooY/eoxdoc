---
id: combineReducers
title: combineReducers
sidebar_label: combineReducers
---
## API
``` javascript
combineReducers({
    a: reducerA,
    b: reducerB,
})
```
## Example
``` javascript
const reducers = combineReducers({
    a: (state, action) => {
        const { type, data } = action
        switch (type) {
            case 'addA':
                return state+1;
            default:
                return state;
        }
    },
    b: (state, action) => {
        const { type, data } = action
        switch (type) {
            case 'addB':
                return state + 1;
            default:
                return state;
        }
    },
})
```
`combineReducers` will combine multi reducers into one.