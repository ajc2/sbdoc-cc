# VAR #
Declare a variable, or obtain variable reference via a functional form.

## Use ##
`VAR varname[=expression][,varname[=expression]...]`  
Declare a variable with name `varname`, and optionally asign it a value.
The assigned value is the result of `expression`.   
An infinite number of declarations can be on one `VAR` statement, and must be separated with a comma.  
Variables must be declared following specific rules (see notes).  
The `DIM` instruction is equivalent.
- - -
`VAR(varname$)`  
Reference a variable named in the string `varname$`.  
This instruction is undocumented, and also has its own rules (see notes).
