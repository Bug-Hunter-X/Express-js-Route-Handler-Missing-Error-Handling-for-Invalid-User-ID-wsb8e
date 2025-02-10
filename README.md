# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input. Specifically, the provided code lacks handling for cases where the user ID is not a valid number. This can lead to unexpected behavior or crashes.

## Bug

The `bug.js` file contains the faulty code.  It attempts to parse the user ID as an integer without checking for errors. If the ID is not a number, `parseInt(userId)` will return `NaN`, and the subsequent comparison `user.id === NaN` will always be false, leading to a `User not found` response even if the ID is simply invalid.

## Solution

The `bugSolution.js` file demonstrates the corrected code.  It includes error handling to check if `parseInt(userId)` results in a valid number before proceeding. If the conversion fails, an appropriate error response is returned.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js` and make requests with invalid user IDs (e.g., non-numeric strings).
4. Compare the behavior to that of `node bugSolution.js`.
