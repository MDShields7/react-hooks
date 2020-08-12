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

Where multiple useState calls exist within a function component, react always calls them in the same order

// ------------
// First render
// ------------
useState('Mary')           // 1. Initialize the name state variable with 'Mary'
useEffect(persistForm)     // 2. Add an effect for persisting the form
useState('Poppins')        // 3. Initialize the surname state variable with 'Poppins'
useEffect(updateTitle)     // 4. Add an effect for updating the title

// -------------
// Second render
// -------------
useState('Mary')           // 1. Read the name state variable (argument is ignored)
useEffect(persistForm)     // 2. Replace the effect for persisting the form
useState('Poppins')        // 3. Read the surname state variable (argument is ignored)
useEffect(updateTitle)     // 4. Replace the effect for updating the title

The number of hooks must not change, that's why we don't put them inside conditional blocks, loops, etc.

Don't put hook in conditional statement, but can put conditional statement inside of hook.

Custom hoooks use shared logic and start with 'useSomething'