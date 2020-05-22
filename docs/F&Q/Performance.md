---
id: Performance
title: About Performance
sidebar_label: About Performance
---
todo

<!-- * How to avoid unneccesary re-render?

when a component call `useContext` , every update on `context` will call our component re-render. 
1 Split contexts that don't change together
2 Split your component in two, put `memo` in between
3 One component with `useMemo` inside
[see this issue](https://github.com/facebook/react/issues/15156) -->