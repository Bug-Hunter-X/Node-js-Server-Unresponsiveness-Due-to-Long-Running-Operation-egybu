# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running operation in the request handler can make the server unresponsive to new requests.  The example uses a simple `while` loop to simulate this scenario.  The solution demonstrates using asynchronous operations to prevent blocking the event loop.

## Bug

The `server.js` file contains a Node.js HTTP server with a request handler that performs a 5-second CPU-bound operation. This blocks the event loop and prevents the server from responding to other requests until the operation completes.

## Solution

The `serverSolution.js` file demonstrates how to solve this using asynchronous operations.  Instead of a blocking `while` loop, it uses `setTimeout` to simulate an asynchronous operation.  This allows the event loop to continue processing other requests while the asynchronous operation is running.