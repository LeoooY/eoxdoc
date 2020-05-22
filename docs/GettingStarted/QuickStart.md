---
id: QuickStart
title: Quick Start
sidebar_label: Quick Start
---

## Step 1: Create a `Provider`  

``` javascript
/* context.js */ 
import { createProvider, combineReducers } from 'eox';

const initState = {
    a: 1,
    b: 100,
}

const reducers = combineReducers({
    a: (state, action) => {
        const { type, data } = action
        switch (type) {
            case 'addA':
                return state + 1;
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

const { Provider, Context } = createProvider(reducers, initState);

export {
    Provider,
    Context,
}
```

## Step 2: Wrap your App with the `Provider`

``` javascript
/* App.js */
import React from 'react';
import { Provider } from 'context.js'

const App = () => {
    return (
        <Provider>
            <Child />
        </Provider>
    )
}
```

## Step 3: Useing Context by `withContext`
``` javascript
/* Child.js */
import React, { useContext } from 'react';
import { withContext } from 'eox';
import { Context } from 'context.js';

const Child = ({ dispatch, counta }) => {
    return (
        <div>
            a:{counta}
            <button onClick={()=>dispatch({ type: 'addA' })}>add a</button>
        </div>
    )
}
export default withContext(Child,Contex,{
    dispatch: ctx => ctx.dispatch,
    counta: ctx => ctx.state.a,
})
```
