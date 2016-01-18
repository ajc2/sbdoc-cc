# EXP #
Return the mathematical constant e, raised to the given power.

## Use ##
`EXP([exponent])`  
Returns the value of e exponentiated by `exponent`.  
If `exponent` is not passed, the constant e is returned.
This is equivalent to passing 1 as the exponent.  
The exact value of e returned is 2.7182818284590451.

## Examples ##
`PRINT EXP()`  
Print the mathematical constant e.

## Notes ##
`EXP()` performs nearly 3 times as fast when not given an argument, even if the argument is 1.
Thus, it may fold to a constant as `A#=EXP()` performs the same as `A#=2.718`.
It is possible that it simply doesn't perform calculation when not given an argument,
and *always* performs calculation when given an argument, even if it is 1.
However, if this explanation were true, it wouldn't account for the lack of calling overhead.
