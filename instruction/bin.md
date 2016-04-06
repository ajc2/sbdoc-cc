# BIN$ #
Get a binary string of the given integer.

***This instruction is coming in 3.3.0.*  
Its function is not confirmed. Assumptions have been made on part of the SmileBASIC community.**

## Use ##
`BIN$(int%{,len%})`  
Returns a string giving the binary representation of the integer `int%`.  
If `len%` is passed, the output string is padded to the given length. Otherwise,
the output is left as-is. If the output is to be longer than the length given in `len%`,
an error will occur.
- - -
`BIN$ int%{,len%} OUT var$`  
Same as above, but in `OUT` syntax. The varaible `var$` takes the output as its value.

## See Also ##
- [HEX$ Instruction](/instruction/hex.md)
