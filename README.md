# React 19 - useSyncExternalStore Incorrect subscribe function signature

This repository demonstrates a bug in React 19 related to the `useSyncExternalStore` hook.  The `subscribe` function within `useSyncExternalStore` must adhere to a specific signature; it must return a cleanup function to properly manage subscriptions.  Failure to do so can lead to unpredictable behavior and rendering issues.

The `bug.js` file contains the erroneous implementation, showcasing the problem. The `bugSolution.js` file presents the corrected implementation, highlighting how to properly return a cleanup function from the `subscribe` callback.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npm start` to start the development server.
4. Observe the incorrect behavior in the `bug.js` component and the corrected behavior in the `bugSolution.js` component.

## Solution

The solution involves ensuring the `subscribe` function in `useSyncExternalStore` returns a function that cleans up the subscription.  This is crucial for preventing memory leaks and ensuring accurate data synchronization.