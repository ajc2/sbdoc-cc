# HEX$ #
Get a hex string representing the given integer.

## Description ##
`HEX$` takes an integer and returns a string of its hexadecimal representation.
For example, the integer 127 will be returned as the string "7F". If a maximum length
is specified, the output will be padded with 0 until it reaches the length.
If the output is already at that length, no 0s are added, and if it is longer
an error is thrown.

## Syntax ##
`HEX$(num%{,length%})`  
Returns the given integer as a hex string.  
If `length%` is passed, leading zeroes are added to
the output string so it's length in charactes matches
`length%`. If the output string will exceed the length
specified, an `Illegal function call` error is thrown.
If `length%` is not passed, the output string is simply
returned as-is.
- - -
`HEX$ num%{,length%} OUT stringvar$`  
Same as above. The result is written to the variable `stringvar$`.

## Examples ##
`PRINT HEX$(16)`  
Prints "10".

## See Also ##
- [BIN$ Instruction](/instruction/bin.md)
