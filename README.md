# React useEffect setInterval Memory Leak

This repository demonstrates a common mistake when using the `setInterval` function within a React `useEffect` hook, leading to a memory leak.  The incorrect implementation creates a new interval on every render, while the correct implementation uses a cleanup function to ensure that only one interval is running at a time and it's cleared when the component unmounts.

## Bug
The `bug.js` file contains the problematic code. The `setInterval` function is not correctly managed within the useEffect hook resulting in memory leak.

## Solution
The `bugSolution.js` file shows the corrected code. The key improvement is the addition of a cleanup function in the `useEffect` hook's return statement. This function clears the interval using `clearInterval` when the component unmounts or when the dependencies change preventing memory leaks. 