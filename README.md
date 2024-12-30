# Express.js JSON Parsing Error

This repository demonstrates a common issue in Express.js applications where JSON request bodies are not parsed correctly when the `Content-Type` header is missing or set incorrectly.

## Bug
The provided `bug.js` file contains an Express.js server that attempts to parse JSON data from a POST request.  If the request doesn't include the `Content-Type: application/json` header, the `req.body` will be empty, resulting in unexpected behavior.

## Solution
The `bugSolution.js` file provides a corrected version.  It addresses the issue by ensuring that the middleware `express.json()` is properly configured. 

## How to Reproduce
1. Clone this repository.
2. Run `npm install` to install express.
3. Run `node bug.js`.
4. Send a POST request to `http://localhost:3000/data` with JSON data in the body but **without** the `Content-Type: application/json` header (or with an incorrect header).
5. Observe that `req.body` is empty, demonstrating the bug.
6. Repeat steps 3-5 but with `node bugSolution.js` and a proper header to observe the correct behaviour. 