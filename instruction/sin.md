# SIN #
Get the sine of the given radian angle.

## Description ##
`SIN` takes an angle in radians as an input, and returns the result of the sine function
for the input as a real number. It is one of three trigonometric functions available in SmileBASIC,
the others being `COS` and `TAN`. Its hyperbolic is `SINH` and it's inverse is `ASIN`.

## Syntax ##
`SIN(rad)`  
Returns the sine of `rad`. `rad` is an angle in radians.
- - -
`SIN rad OUT var#`  
`var#` takes the sine of `rad` as its value.

## Examples ##
```
SINE=SIN(20)
PRINT SINE
```
Prints the sine of 20 radians.
