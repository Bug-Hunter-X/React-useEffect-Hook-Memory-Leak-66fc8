# React useEffect Hook Memory Leak

This repository demonstrates a common, yet subtle, bug in React applications involving the `useEffect` hook.  Specifically, it showcases a missing `return` statement within a cleanup function, leading to potential memory leaks.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected implementation.  This example highlights the importance of using the cleanup function in `useEffect` to prevent resources from remaining allocated after a component unmounts.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console output.  The 'Component mounted' message will appear, but there will be no 'Component unmounted' message when the component is removed from the DOM (e.g., by navigating away).

## Solution

The corrected code (in `bugSolution.js`) includes a return function that performs cleanup before the component is unmounted, preventing memory leaks.