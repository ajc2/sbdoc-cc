# PRINT #
Prints text on the console. Where the text appears depends on the current cursor location.

## Syntax ##
`PRINT {expression,expression...}`  
Prints the results of all expressions on the console, in order.
There is no hard limit on the number of expressions you can pass.
If no expressions are passed, then the behavior is equivalent to printing an empty string.
The separator character between expressions determines the printing behavior.  
- If a `,` is placed between expressions, then the output of each expression will be
  horizontally spaced based on `TABSTEP`, as if a tab character was placed between them.
- If a `;` is used instead, no spacing will be added. This is equivalent to setting `TABSTEP` to 0.

If a separator is placed after the last expression, the print cursor is moved ahead
based on that separator's behavior, and not moved to the next line.
Otherwise, the print cursor is automatically moved to the next line afterwards.
`?` can be used in place of `PRINT`.

## Examples ##
`PRINT "Hello world!"`  
Prints `Hello world!` on the console.
- - -
`PRINT "A","B"`  
Prints the letter A, then prints B, horizontally aligned based on `TABSTEP`.
- - -
`PRINT 5+5;2`  
Prints `102`.
