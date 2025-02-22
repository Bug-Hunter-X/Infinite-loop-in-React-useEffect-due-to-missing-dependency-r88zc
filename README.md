# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by a missing dependency array.  The `useEffect` hook, without a dependency array or with an incomplete one, will re-run after every render, leading to performance issues or even crashes. This example showcases the problem and its solution.

## Bug

The `bug.js` file contains a component with an `useEffect` hook that logs the current count. Without the dependency array `[count]`, the effect runs on every render, causing the `console.log` to trigger endlessly.  This is because the effect doesn't know which values to watch for changes, leading to infinite rerenders.

## Solution

The `bugSolution.js` file shows the corrected version. The dependency array `[count]` tells the `useEffect` hook to only re-run when the `count` state variable changes. This fixes the infinite loop.