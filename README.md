# React setInterval Memory Leak Bug

This repository demonstrates a common bug in React applications involving the use of `setInterval` within the `useEffect` hook without proper cleanup.  This leads to a memory leak as the interval continues to run even after the component unmounts.

## Bug Description

The `MyComponent` component uses `setInterval` to update a counter every second. However, it lacks a cleanup function in the `useEffect` hook to stop the interval when the component is unmounted. This results in the interval continuing to run indefinitely, leading to a memory leak and potential performance issues.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter in the browser. Even if the component is unmounted, the counter continues to increment in the console.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook to clear the interval when the component unmounts. This ensures that the interval is properly stopped, preventing memory leaks.

## Learning Outcomes

This example highlights the importance of proper cleanup in `useEffect` when using timers or other asynchronous operations.  Ignoring cleanup can lead to subtle but significant bugs that are difficult to debug.