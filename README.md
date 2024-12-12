# React Memory Leak: setInterval in useEffect without Cleanup

This repository demonstrates a common React bug: a memory leak caused by using `setInterval` within the `useEffect` hook without a cleanup function.  The component continuously increments a counter every second, leading to a memory leak because the interval isn't cleared when the component unmounts.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version with a cleanup function.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the console in the browser's developer tools for any warnings or errors.  Note that the memory leak might not be immediately obvious, but leaving the app running for a while will eventually show the increasing memory consumption.

## Solution

The solution involves using a cleanup function in the `useEffect` hook's return statement to clear the interval when the component unmounts or when the effect dependencies change.