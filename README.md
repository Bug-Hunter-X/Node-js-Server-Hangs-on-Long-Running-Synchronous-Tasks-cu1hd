# Node.js Server Hang on Long-Running Tasks

This repository demonstrates a common issue in Node.js applications where long-running synchronous operations can block the event loop, leading to unresponsive servers.  The `bug.js` file shows the problem, while `bugSolution.js` provides a solution using asynchronous operations and appropriate event loop management.

## Problem

Node.js is single-threaded, relying on an event loop to handle asynchronous operations.  When a long-running synchronous task is executed, it blocks the event loop, preventing other events (such as incoming requests) from being processed. This leads to a frozen or unresponsive server.

## Solution

The solution involves refactoring the code to use asynchronous operations or breaking down long tasks into smaller chunks that allow the event loop to continue processing other events.

## How to Reproduce

1. Clone this repository.
2. Run `node bug.js` and attempt to access `http://localhost:3000` in a browser. You'll observe the server hangs.
3. Run `node bugSolution.js` to see the corrected behavior.