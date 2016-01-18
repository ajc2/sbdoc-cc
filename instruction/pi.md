# PI #
Get the value of π (pi).

## Use ##
`PI()`  
Returns the value of π. Precisely, it returns 3.1415926535897931.

## Examples ##
`VAR#=PI()`  
The variable `VAR#` now has the value of π.

## Notes ##
`PI()` does not have an associated `OUT` form and does not have syntax highlighting in the editor.
This, along with the fact that `PI` can be used as a `DEF` name with little restriction,
has interesting implications. It is possible that the dev team simply made mistakes while implementing `PI()`,
or maybe that it is not implemented in the same way as a regular instruction.  
Speed tests imply that `PI()` may be compiled to a constant, as `A#=PI()` performs just as quickly as `A#=3.14`.
This can be explained by assuming that `PI()` only serves to return the value
(and thus performs very quickly), but one would expect calling overhead to affect speed.
