# JavaScript Closure Issue with setTimeout

This repository demonstrates a common error in JavaScript related to closures and the `setTimeout` function.  The code intends to log numbers 0 through 9 to the console with a one-second delay between each number. However, due to a closure issue, all numbers logged will be 10.

## The Problem

The issue stems from how JavaScript handles closures and variable scoping within asynchronous operations.  The `setTimeout` callback function creates a closure over the variable `i`. By the time the `setTimeout` callbacks finally execute, the `for` loop has already completed, and `i` has reached its final value of 10.

## The Solution

The solution involves using an Immediately Invoked Function Expression (IIFE) or `let` to create a new scope for each iteration of the loop, ensuring each callback captures its own unique value of `i`.

## How to run

1. Clone this repository.
2. Open `bug.js` to see the buggy code.
3. Open `bugSolution.js` to see the fixed code.
4. Run the code in a JavaScript environment (e.g., Node.js) to see the results.