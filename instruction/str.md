# STR$ #
An instruction for converting a number to a string.

## Use ##
`STR$(num)`  
The function returns a string representation of `num`.
Throws `Type mismatch` when `num` is a string.
- - -
`STR$ num OUT var$`  
The string variable `var$` is set to a string representation of `num`.
Throws `Type mismatch` when `num` is a string or `var$` is a number variable.

## Examples ##
`PRINT STR$(5)`  
5 is printed on the console.
- - -
`STR$ 10 OUT A$`  
The variable `A$` is assigned the string "10".

## Notes ##
- `FORMAT$()` can also be used to convert a number to a string, and is more flexible. Thus, it might be preferred in some situations.
- `STR$ OUT` is not in the official documentation.
