# Unresponsive Node.js Server Due to Blocking I/O

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler blocks the event loop, making the server unresponsive.  The `bug.js` file contains the problematic code, while `bugSolution.js` shows how to fix it using asynchronous operations.

## Problem

Node.js is single-threaded, meaning it uses a single thread to handle all requests.  If a request handler performs a long-running synchronous operation (like the 5-second `while` loop in `bug.js`), it blocks the event loop, preventing other requests from being processed.  This makes the server appear unresponsive.

## Solution

The solution involves using asynchronous operations instead of synchronous ones.  The `bugSolution.js` file demonstrates this using `setTimeout`. Asynchronous operations allow the event loop to continue processing other requests while the long-running task is being executed in the background.