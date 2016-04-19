# CLIPBOARD #
Access the editor clipboard.

***This feature is coming in 3.3.0.*  
Its function is not confirmed.
Assumptions have been made on the part of the SmileBASIC community.**

## Description ##
`CLIPBOARD` allows the user to read and write the string
in the editor's copy/paste clipboard. This clipboard is
used when performing a cut, copy, or paste in the program
editor; using this, people can make toolkits to generate
signatures or timestamps for posting into code, or for
recovering lost text you may have forgotten you copied.

## Syntax ##
`CLIPBOARD` allows both reading and writing.
### Setting the string ###
`CLIPBOARD str$`  
The editor clipboard is set to `str$`.
When pasting into the editor, this string will be the value.

### Getting the string ###
`CLIPBOARD()`  
Returns the string in the clipboard.
When cutting or copying in the editor, that text will be
written to the clipboard.
- - -
`CLIPBOARD OUT var$`  
The variable `var$` will take the string in the clipboard as its value.
