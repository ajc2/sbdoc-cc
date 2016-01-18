# COPY #
An instruction for copying data from one iterable variable to another,
or for loading DATA into an iterable variable.  
An iterable variable is either an array of any type, or a string.

## Use ##
`COPY dest,[destofs%,]src[,srcofs%[,amount%]]`  
The data in the iterable variable `src` will be copied into the iterable variable `dest`.  
If `destofs%` is passed, the copy will write the data into the destination starting at index `destofs%`.
Otherwise, the data is written starting at index 0.  
If `srcofs%` is passed, the source data will be read starting from the index `srcofs%`.
Otherwise, the read will start at index 0.  
If `amount%` is passed, only `amount%` values will be copied. Otherwise, all of `src%` will be copied.  
- - -
`COPY dest,[destofs%,]@label[,amount%]`  
The contents of `dest` will be overwritten with the `DATA` starting at `@label`.  
If `destofs%` is passed, the copy will write the data into the destination starting at index `destofs%`.
Otherwise, the data is written starting at index 0.  
If `amount%` is passed, only `amount%` values will be copied.
Otherwise, enough `DATA` to fill `dest` will be copied.

## Examples ##


## Notes ##
### Type assumption and compatibility ###
The types of `src` and `dest` must match (like always, however, numeric types are interoperable).
Thus, if `dest` is a string it is assumed that `src` is a string and not a label.
This means it is impossible to copy `DATA` directly into a string.
