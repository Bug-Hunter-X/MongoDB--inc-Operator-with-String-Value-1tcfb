# MongoDB $inc Operator with String Value
This example demonstrates an uncommon error in MongoDB when using the `$inc` operator with a string value instead of a numeric value.  The `$inc` operator is used to increment a numeric field by a specified value.  Passing a string will lead to unpredictable results and is a subtle bug that can be hard to find.

## Bug
The original code attempts to increment a field using `$inc` with a string value ('1'). This does not increment the value, instead it will likely be added as a string.  Refer to `bug.js` for the problematic code.

## Solution
The solution involves ensuring the value being passed to the `$inc` operator is a number (integer or floating point).  Refer to `bugSolution.js` for the corrected code.

## How to reproduce
1.  Clone this repository.
2.  Ensure that MongoDB is running.
3.  Run `bug.js` and observe the unexpected result.
4.  Run `bugSolution.js` and observe the correct result.