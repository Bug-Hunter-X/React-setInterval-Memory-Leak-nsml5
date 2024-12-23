# React setInterval Memory Leak

This repository demonstrates a common mistake when using `setInterval` in React components: failing to properly clear the interval, leading to memory leaks. 

The `bug.js` file showcases the problematic code. The `bugSolution.js` file shows the correct way to handle `setInterval` to avoid memory leaks.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`. Observe the count continuously incrementing, even after unmounting the component.

## Solution

The solution involves storing the interval ID and clearing it in the cleanup function of `useEffect`. This ensures the interval is stopped when the component unmounts or when the dependency changes, preventing memory leaks.