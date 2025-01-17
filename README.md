# COBOL Data Type Mismatch Example

This repository demonstrates a potential data type mismatch issue in a COBOL program. The `bug.cob` file contains code that subtracts a potentially positive number from a numeric field defined with a PIC 9(5) clause (unsigned). This could lead to an unexpected result or program termination. The `bugSolution.cob` file shows how to correct it.

## Bug Description
The program initializes two numeric fields, `WS-AREA-1` and `WS-AREA-2`. It then adds 1 to `WS-AREA-1` and subtracts its value from `WS-AREA-2`.  Because `WS-AREA-2` is defined as an unsigned numeric field, subtracting a value larger than its initial value may result in a negative number which it cannot hold, leading to an error or unexpected behavior.

## Solution
The solution involves changing the PIC clause of `WS-AREA-2` to allow for negative values, such as `PIC S9(5)`. This ensures that the subtraction operation can produce negative numbers without data type violation.