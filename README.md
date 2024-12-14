# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook: an infinite loop caused by incorrectly updating state within the effect's callback.  The bug occurs because the state update triggers a re-render, which in turn re-executes the effect, leading to a never-ending cycle.

## Bug Description
The `bug.js` file contains a component that uses `useEffect` to increment a counter.  However, the counter is updated within the effect without specifying any dependencies in the dependency array (`[]`). This creates an infinite loop as the state change causes the component to re-render continuously. 

## Solution
The solution is presented in `bugSolution.js`.  The dependency array is adjusted to include the `count` state variable, causing the effect to run only once after the component mounts, and then no more unless count changes via other means.