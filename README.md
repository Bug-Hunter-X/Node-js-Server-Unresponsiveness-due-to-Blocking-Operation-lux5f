# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation within the request handler.  The event loop is blocked, leading to poor performance and inability to handle new requests.

## Bug

The `server.js` file contains a simple HTTP server with a computationally expensive loop in the request handler.  This loop blocks the event loop, causing the server to hang after the first request.

## Solution

The `server-solution.js` demonstrates the correct approach: using asynchronous operations or offloading long-running tasks to worker threads to prevent blocking the event loop. This ensures responsiveness and efficient handling of multiple requests.

## How to reproduce

1. Clone the repository
2. Navigate to the `bug` directory
3. Run `node server.js`
4. Send a request to the server (e.g., using `curl http://localhost:3000`)
5. Observe that the server becomes unresponsive to further requests.

Now, repeat steps 2-4 using `server-solution.js` and see the difference.