# PRINT #
Prints text on the console. Where the text appears depends on the current cursor location.

## Use ##
`PRINT [expression, expression...]`  
Prints the results of all expressions on the console.
There is no hard limit on the number of expressions you can pass.  
The separator character between expressions determines the printing behavior.  
If a `,` is placed between expressions, then a number of spaces
(equal to `TABSTEP`) is placed between the expressions when printed.  
If a `;` is used instead, no spaces will be added. This is equivalent to setting `TABSTEP` to 0.  
`?` can be used in place of `PRINT`.

## Examples ##
`PRINT "Hello world!"`  
Prints `Hello world!` on the console.
- - -
`PRINT "A","B"`  
Prints the letter A, then prints B
with a number of spaces before it (4 by default).
- - -
`PRINT 5+5;2`
Prints `102`.

## Notes ##
It is generally recommended to use `?` instead to keep code shorter.
