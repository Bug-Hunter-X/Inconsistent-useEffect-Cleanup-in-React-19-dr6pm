# Inconsistent useEffect Cleanup in React 19

This repository demonstrates a bug where the cleanup function in React 19's `useEffect` hook does not always run consistently before the next effect.  This can lead to memory leaks or unexpected behavior, especially when dealing with asynchronous operations or complex state updates.

## Problem Description

The `useEffect` hook in React 19 is supposed to run a cleanup function before the next effect. However, in certain scenarios (especially with frequent state updates or asynchronous operations), this cleanup function is not always guaranteed to run, potentially leading to unintended side effects.

## Steps to Reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Rapidly click the button multiple times. Observe that the console logs sometimes skip the 'Cleanup function ran' message. This indicates the cleanup function is not always being invoked.

## Solution

The provided solution in `bugSolution.js` offers a robust approach to ensure consistent cleanup function execution by using a more controlled state update strategy.