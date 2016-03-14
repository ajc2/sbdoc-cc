# INC #
Increment a variable's value by a given expression.

## Syntax ##
`INC variable{,expression}`  
Increments the value of `variable` by the result of `expression`.
If `expression` is not passed, it is the number 1.  
The behavior of incrementing is dependent on type.
- If the variable is a number, the result of `expression` is added to the number.  
  e.g. If `variable` is 10 and `expression` is 5, `variable` becomes 15.
- If `variable` is a string, the result of `expression` is concatenated to the
  end of `variable`.  
  e.g. If `variable` is "test" and `expression` is "A", variable becomes "testA".

Both `variable` and `expression` must be of compatible type. If not, `Type mismatch`
will be thrown.
