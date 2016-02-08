# RND #
Generate a random integer.

## Use ##
`RND({id%,}limit%)`  
Returns a random integer greater-than or equal-to 0,
and less than `limit%`. If `id%` is passed, the RNG specified
will be used to generate the number. Otherwise, RNG 0 is used
by default.
- - -
`RND {id%,}limit% OUT intvar%`  
Same as above. The generated number is written to `intvar%`.

## Examples ##
`PRINT RND(10)`  
Prints a random number between 0 and 9.
- - -
`RND 5,5 OUT I%`  
A random number between 0 and 4 is written to I%.
RNG 5 is used to generate the number.

## See Also ##
- [Random Number Generation](/sysdoc/rand.md)
