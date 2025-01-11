# React useEffect Cleanup Function Issue

This repository demonstrates a problem with the cleanup function in React's `useEffect` hook.  The expected behavior is that the cleanup function should execute before the next effect runs or when the component unmounts. However, in this specific example, the cleanup function is not consistently behaving as intended.

## Problem Description

The provided `MyComponent` uses `useEffect` to log the current count and a cleanup message.  While the count logging works as expected, the cleanup message is not reliably displayed. This inconsistency arises because of how the effect's dependency array and the component's lifecycle interact. 

## Solution

The solution involves understanding the dependency array in useEffect. The dependency array determines when the effect should run.  If omitted or set to empty array `[]`, the effect will run after every render. Incorrectly managing this array can lead to unexpected behavior, such as the cleanup function not executing at the appropriate times.

The solution is in the `bugSolution.js` file.