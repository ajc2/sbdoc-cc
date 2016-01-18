# REM #
Marks text as a comment.

## Use ##
`REM [text]`  
The text after REM is considered a comment, up to the end of the line,
and thus ignored by the precompiler.

## Examples ##
`REM Comment`  
This line is a comment and ignored by the precompiler.
- - -
`PRINT "AYY" REM output text`
The text after the `PRINT` statment is ignored, creating an inline comment.

## Notes ##
`REM` should never be used. Instead, the comment character `'` should be used.
It can be used any way `REM` can, and even adds syntax highlighting to the comment.
