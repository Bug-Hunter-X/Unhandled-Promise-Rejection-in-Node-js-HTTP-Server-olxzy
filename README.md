# Unhandled Promise Rejection in Node.js HTTP Server

This repository demonstrates a common error in Node.js applications: unhandled promise rejections.  The example shows an HTTP server that performs an asynchronous operation.  If the operation fails, the server crashes without proper error handling.

## Bug

The `bug.js` file contains a Node.js HTTP server that uses a promise to simulate an asynchronous operation. If the promise rejects, the error is not caught, resulting in an unhandled promise rejection.  This will likely crash the application without any meaningful error message in production.

## Solution

The `bugSolution.js` file demonstrates the corrected code. The `catch` block in the promise properly handles the rejection, preventing the application from crashing.  A more robust solution might also log the error, display an error page to the client, or implement more sophisticated error monitoring.

## How to Reproduce

1. Clone this repository.
2. Run `node bug.js`.
3. Refresh the page several times. You'll eventually encounter an unhandled promise rejection and the server will likely crash.
4. Run `node bugSolution.js`. This version handles the error correctly.

## Lessons Learned

Always handle promise rejections using `.catch()`.  Ignoring them can lead to unexpected crashes and instability in production.  Implement proper logging and error monitoring to detect and resolve issues promptly.