# React useEffect Runs on Every Render

This repository demonstrates a common issue in React applications where the `useEffect` hook runs on every render, even when the dependencies array is omitted or incorrect, causing performance problems.

## Problem

The provided `bug.js` file contains a `MyComponent` that uses the `useEffect` hook without specifying a dependencies array.  This causes the effect to run after every render, logging 'Effect ran!' to the console unnecessarily.  For simple components this might not be a problem, but in complex components with expensive operations in the effect, this can lead to significant performance degradation.

## Solution

The `bugSolution.js` file provides a corrected version. By including an empty array `[]` as the second argument to `useEffect`, we ensure the effect only runs once after the initial render.