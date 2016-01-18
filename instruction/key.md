# KEY #
Get or set the string on the function keys.
The function keys are numbered 1 - 5 from left to right.  
The function of the SHIFT function keys cannot be changed.

## Use ##
`KEY fkey%,string$`  
The contents of `string$` is mapped to the function key `fkey%`.
- - -
`KEY(fkey%)`  
Returns the string associated with `fkey%`.
- - -
`KEY fkey% OUT stringvar$`  
The string variable `stringvar$` is given the string associated with `fkey%`

## Examples ##
`PRINT KEY(1)`  
The string on F1 is printed to the console (by default, this is "FILES".)
- - -
`KEY 2,"HELLO"`  
The string on F2 is set to "HELLO".

## Notes ##
The getters for `KEY` are not documented in the official documentation.
