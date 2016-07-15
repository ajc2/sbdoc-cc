# ARYOP #
Perform basic math operations on arrays.

***This instruction is part of the Sound Unit DLC pack.*  
An additional purchase is required to use this instruction in SmileBASIC.**

## Description ##
`ARYOP` performs a math operation using a number of inputs,
based on its set operating mode. This result is computed per every
index in the output array.

## Syntax ##
In its most simplified form, `ARYOP` takes the syntax `ARYOP mode%,outArr[],arglist...`
where `arglist` is a set of inputs dependent on operation mode.
Each operation mode will be described here separately, named by its associated constant.
### #AOPADD ###
`ARYOP #AOPADD,outArr[],augend,addend`  
The value of `addend` is added to the augend and the result is
stored in `outArr[]`.  
This would be equivalent to `outArr[i%]=augend+addend`,
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
