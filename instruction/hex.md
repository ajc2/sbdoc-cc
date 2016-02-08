# HEX$ #
Get a hex string representing the given integer.

## Use ##
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
