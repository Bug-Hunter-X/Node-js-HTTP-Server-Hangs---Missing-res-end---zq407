# Node.js HTTP Server Hang: Missing res.end()

This repository demonstrates a common error in Node.js HTTP servers: forgetting to call `res.end()` to signal the completion of the response.  This can lead to the server hanging and failing to respond to subsequent requests.

The `bug.js` file contains the erroneous code, while `bugSolution.js` provides the corrected version.

## Reproducing the Bug
1. Run `node bug.js`
2. Make a request to `http://localhost:3000`
3. Observe that the server responds but subsequent requests will hang.

## Solution
The solution is simply to add `res.end()` to the HTTP response.  This signals to the client that the response is complete, allowing the server to handle further requests.