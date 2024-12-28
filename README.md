# JavaScript Closure Issue with `setTimeout`

This repository demonstrates a common JavaScript closure issue related to the use of `setTimeout` within a loop. The example showcases how the variable `i` is not captured properly, leading to unexpected output.

## Problem

The `myFunction` uses a loop and `setTimeout` to log the value of `i` after a delay.  However, due to how closures and the timing of the `setTimeout` callbacks work, the final value of `i` (10) is logged in every iteration rather than the expected values from 0 to 9. This is because `setTimeout`'s callbacks only execute after the loop has completed.

## Solution

The solution involves creating an immediately-invoked function expression (IIFE) that captures the current value of `i` in each loop iteration.  This ensures that each `setTimeout` callback uses its own copy of `i`, maintaining the intended value for each log.

## How to run

1. Clone this repository.
2. Open `bug.js` to see the buggy code and `bugSolution.js` to view the corrected code.
3. Run the files in a JavaScript environment (like a browser's console or Node.js).