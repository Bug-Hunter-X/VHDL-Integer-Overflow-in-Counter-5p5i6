# VHDL Integer Overflow Bug

This repository demonstrates a potential integer overflow bug in VHDL and its solution.

## Bug Description
The `buggy_counter.vhd` file contains a counter implemented using the `integer` type.  While a range is specified for `internal_count`, many VHDL implementations don't enforce strict range checking on all integer operations.  This can lead to unexpected behavior or simulation errors if the counter exceeds its intended range.

## Solution
The `fixed_counter.vhd` file provides a solution using `unsigned` type for better range control within the VHDL language.  Unsigned types provide inherent range checks, preventing unexpected behavior when the counter reaches its upper bound.  Consider using unsigned or other bounded integer types for counters where overflow is a concern.

## How to reproduce
Simulate `buggy_counter.vhd` and observe the behavior when the counter reaches 15.  Then, simulate `fixed_counter.vhd` and compare the results to see the difference and improved range checking in the corrected version.  Most VHDL simulators will display warnings or errors with the 'integer' type if the code is not handled carefully.