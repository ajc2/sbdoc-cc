# CLIPBOARD #
Access the editor clipboard. Cut/copy/paste operations
in the editor will use this value.

***This feature is coming in 3.3.0.*  
Its function is not confirmed.
Assumptions have been made on the part of the SmileBASIC community.**

## Use ##
`CLIPBOARD str$`  
The editor clipboard is set to `str$`.
When pasting into the editor, this string will be the value.
- - -
`CLIPBOARD()`  
Returns the string in the clipboard.
When cutting or copying in the editor, that text will be
written to the clipboard.
- - -
`CLIPBOARD OUT var$`  
The variable `var$` will take the string in the clipboard as its value.
