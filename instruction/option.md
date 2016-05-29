# OPTION #
Controls the behavior of the SmileBASIC preprocessor.

## Use ##
`OPTION COMPAT | DEFINT | STRICT | TOOL`  
Sets the behavior of the preprocessor according to the given option.
The option given can be only one of the following:
- `COMPAT`: *Coming in Wii U version.* Puts the preprocessor in compatibility mode (see notes in the future.)
- `DEFINT`: Unsuffixed variables are assumed to be integer-type, instead of the default real-type.
- `STRICT`: The preprocessor will throw an error when encountering an undeclared variable
  instead of creating a reference to it.
- `TOOL`: Previously used to indicate the program was a tool program. Currently does nothing.

Note that `OPTION` only takes effect on the code that comes after it.

## Examples ##
`OPTION DEFINT`  
All unsuffixed variables are assumed to be integers after this instruction.

## Notes ##
### OPTION TOOL ###
`OPTION TOOL` was previously part of the requirements of mapping a tool program to the Smile Button.
Now that any program can be mapped to the key from the Options menu, `TOOL` serves no purpose.
