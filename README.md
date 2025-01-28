# Stale Closure in React's useEffect Hook

This example demonstrates a common error in React's `useEffect` hook: using a stale closure.  The `setInterval` callback uses the initial value of the `count` state variable instead of the latest value, leading to unexpected behavior.

## Problem

The code in `bug.js` attempts to increment a counter every second. However, because the `setInterval` callback uses the initial value of `count` from the closure, the counter will always increment from 0 instead of the current value.

## Solution

The solution is to use a functional update within the `setCount` function: `setCount(prevCount => prevCount + 1);`. This ensures that the latest value of `count` is always used to increment.

## How to reproduce:

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that the counter increments incorrectly in the initial file and correctly in the solution file.