# Uncontrolled Infinite Loop in React Component
This repository demonstrates a common React bug caused by the improper use of the `useEffect` hook.  The example shows how forgetting to specify a dependency array in `useEffect` can lead to an infinite re-render loop, impacting performance and potentially causing your application to crash.

## Bug Description
The `useEffect` hook, without a dependency array, runs after every render.  In this case, it triggers a console log and an infinite loop.  Because `count` is always changing, this effect keeps re-running, triggering a new render, leading to an uncontrolled infinite loop.

## How to reproduce
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the infinite console logs and the extremely high CPU usage in your browser's developer tools.

## Solution
The solution involves correctly specifying the dependency array in the `useEffect` hook.  The array lists the values the effect depends on. If the array is empty (`[]`), the effect runs only once after the initial render. If it contains variables, the effect runs whenever those variables change.