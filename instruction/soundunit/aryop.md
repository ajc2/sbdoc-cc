# ARYOP #
Perform basic math operations on arrays.

***This instruction is part of the Sound Unit DLC pack.*  
An additional purchase is required to use this instruction in SmileBASIC.**

## Description ##
`ARYOP` performs a math operation on a given array using a number of inputs,
based on its set operating mode. The operating modes are as follows:
- `#AOPADD` - Adds a constant value to every element of an array
- `#AOPSUB` - Subtracts a constant value from every element of an array
- `#AOPMUL` - Multiplies every element of an array by a constant value
- `#AOPDIV` - Divides every element of an array by a constant value
- `#AOPMAD` - Multiply and Add (description to come)
- `#AOPLIP` - Linear Interpolate (description to come)
- `#AOPCLP` - Clamps all values in an array to a specified range

## Syntax ##
In its most simplified form, `ARYOP` takes the syntax `ARYOP mode%,inArr[],outArr[],arglist...`
where `arglist` is an additional set of inputs dependent on the operation mode.
Each operation mode will be described here separately, named by its associated constant.
### #AOPADD ###
`ARYOP #AOPADD,inArr[],outArr[],addend`  
The value of `addend` is added to every value in `inArr[]` and the result is
stored in `outArr[]`.  
This would be equivalent to `outArr[i%]=inArr[i%]+addend`,
where `i%` is the array index.
### #AOPSUB ###
`ARYOP #AOPSUB,inArr[],outArr[],subtrahend`  
The value of `subtrahend` is added to every value in `inArr[]` and the result is
stored in `outArr[]`.  
This would be equivalent to `outArr[i%]=inArr[i%]-subtrahend`,
where `i%` is the array index.
### #AOPMUL ###
`ARYOP #AOPMUL,inArr[],outArr[],multiplier`  
Every value in `inArr[]` is multiplied by `multiplier`, and the result is
stored in `outArr[]`.  
This would be equivalent to `outArr[i%]=inArr[i%]*multiplier`,
where `i%` is the array index.
### #AOPDIV ###
`ARYOP #AOPDIV,inArr[],outArr[],divisor`  
Every value in `inArr[]` is divided by `divisor`, and the result is
stored in `outArr[]`.  
This would be equivalent to `outArr[i%]=inArr[i%]/divisor`,
where `i%` is the array index.
### #AOPMAD ###
Description not available right now.
### #AOPLIP ###
Description not available right now.
### #AOPCLP ###
`ARYOP #AOPCLP,inArr[],outArr[],lower,upper`  
Every element in `inArr[]` is clamped to the range `lower <= x <= upper`,
and the result is written to `outArr[]`.  
In other words, if the value is less than `lower`, it is set to `lower`,
and if the value is greater than `upper`, it is set to `upper`.  
This is equivalent to `outArr[i%]=MAX(MIN(inArr[i%],upper),lower)`,
where `i%` is the array index.
