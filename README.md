# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, this example showcases a scenario where a route handler attempts to access a user by ID, without handling cases where the ID is not a valid number, leading to potential crashes or unexpected behavior.  The solution includes robust error handling to gracefully manage such situations.

## Bug

The `bug.js` file contains the flawed route handler. It attempts to parse the `userId` from the request parameters and access the corresponding user from the `users` array. However, it fails to handle the case where `userId` is not a valid number, which leads to an error.  This can manifest as a server crash or an unexpected response.

## Solution

The `bugSolution.js` file provides a corrected version.  It includes a `try...catch` block to handle potential `NaN` errors (if userId is not an integer) resulting from `parseInt`, thereby preventing crashes and providing a more user-friendly response in case of invalid input.