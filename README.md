# React setInterval Memory Leak

This repository demonstrates a common error in React applications: using `setInterval` within a `useEffect` hook without proper cleanup. This leads to memory leaks and unexpected behavior.

## Problem

The `MyComponent` component uses `setInterval` to update the count every second. However, it fails to clear the interval when the component unmounts. This means that even after the component is removed from the DOM, the interval continues to run, consuming resources and potentially causing unexpected side effects.

## Solution

The solution involves using the return value of `useEffect` to clear the interval when the component unmounts. This ensures that the interval is stopped when it is no longer needed.