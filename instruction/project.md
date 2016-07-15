# PROJECT #
A family of instructions for getting and setting the active project.

## Syntax ##
### Setting the Active Project ###
`PROJECT string$`  
Sets the active project to the one named in `string$`. DIRECT Mode only.
### Getting the Active Project ###
`PROJECT()`  
Returns the name of the active project as a string.
- - - 
`PROJECT OUT stringvar$`  
The variable `stringvar$` is set to the name of the current project.

## Examples ##
`PRINT PROJECT()`  
Prints the name of the active project.
- - -
`PROJECT "HELLO"`  
Sets the active project to `HELLO`.

## Notes ##
### Project Naming Rules ###
Projects follow the same name rules as files.
- The name may contain only capital Latin letters, numbers, underscores, and hyphens.
- The name must be between 1 and 14 characters.

### Documentation ###
`PROJECT OUT` is not in the official documentation.
