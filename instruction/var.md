# VAR #
Declare a variable, or obtain variable reference via a functional form.

## Use ##
`VAR varname{=expression}{,varname{=expression}...}`  
Declare a variable with name `varname`, and optionally asign it a value.
The assigned value is the result of `expression`.   
An infinite number of declarations can be on one `VAR` statement, and must be separated with a comma.  
Variables must be declared following specific rules (see notes).  
The `DIM` instruction is equivalent.
- - -
VAR arrayname[size0%{,size1%{,size2%{,size3%}}}]  
Declare an array of the given dimensions and size.
Up to 4 dimensions can be used. size0% is the size of the first
dimension, size1% the second, etc. At least 1 dimension is
required.
- - -
`VAR(varname$)`  
Reference a variable named in the string `varname$`.  
This instruction is undocumented, and also has its own rules (see notes).
