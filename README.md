This project was bootstrapped with 
[React Hooks Overview](https://reactjs.org/docs/hooks-overview.html).

## useEffect
A single API to serve same purposes as componentDidMount, componentDidUpdate, componentWillUnmount.

Don't call hooks inside loops, conditions, or nested function - **only** at top level.

**Only** call hooks from React function components.

Each call to a hook component has a separate state.

Updating state variables replaces state instead of merging.

The function may complete, but the state is preserved in React.

useEffect(() => {
  document.title = `You clicked ${count} times`;
}, [count]);

Extra [count] after comma calls for re-render only if count changes.