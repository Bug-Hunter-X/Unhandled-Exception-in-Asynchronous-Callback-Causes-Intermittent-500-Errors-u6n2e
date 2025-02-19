# Unhandled Exception in Asynchronous Callback

This repository demonstrates a common error in Node.js applications: unhandled exceptions within asynchronous callbacks.  The server simulates an operation that randomly succeeds or fails.  Without proper error handling, failures lead to intermittent 500 errors.

## Bug

The `bug.js` file contains the erroneous code.  The asynchronous operation inside the `setTimeout` callback lacks error handling, causing the server to crash if the random condition results in failure. This leads to inconsistent behavior.

## Solution

The `bugSolution.js` file demonstrates the correct way to handle potential errors by wrapping the asynchronous operation in a `try...catch` block, or using promises and `.catch()` for better error handling.  This ensures that even if an error occurs, the server responds gracefully and doesn't crash.

## How to Run

1. Clone this repository.
2. Navigate to the repository's directory.
3. Run `node bug.js` to see the buggy behavior (intermittent 500 errors).
4. Run `node bugSolution.js` to see the corrected, robust behavior.