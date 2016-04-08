# LOAD #
Instructions for loading files.

***This instruction has recieved changes as of version 3.3.0.*  
A brief summary of those changes is listed here.**
- When loading GRP, a destination offset can be specified in the GRP layer

## Description ##
`LOAD` allows the user to load various types of resource files
within the SmileBASIC file system. These files include:
- `TXT` files, which contain text (`TXT`) or program source code (`PRG`).
- `DAT` files, which contain a numeric array (`DAT`) or a graphic page image (`GRP`).

When loading, the first argument is always the file path string `fpath$`; this
string describes both the resource loading mode of `LOAD` as well as location of the
source file. The format of `LOAD` that follows is dependent on the resource type.  
`fpath$` takes the form `resc:{project/}filename`, where `resc:` is the resource prefix,
`{project/}` is an optional project path (see notes), and `filename` is the name of the
source file at that location.  
The last argument to `LOAD`, however, is always the same. It is an optional argument
`dlg%`; when true or not passed, the load confirmation dialog will display.
When false, the load confirmation dialog is hidden.

## Syntax ##
As described above, the syntax of `LOAD` is dependent on use case.
Each will be described here.

### Loading Programs (PRG) ###
`LOAD fpath${,dlg$}`  
Loads the TXT file at `fpath$` as source code into a program slot. The file at
`fpath$` must be either a TXT or PRG, or an error will occur.
The resource prefix at the beginning of `fpath$` must take one of the following forms:
- None; specifying no resource prefix defaults `LOAD` to PRG mode.
- `PRG:` - This will load the program into slot 0 (does not work in tool slot)
- `PRG%:`, where `%` is a valid slot number (0-3)
  - e.g. `PRG1:HELLO` will load the TXT file HELLO to slot 1.

### Loading Text Strings (TXT) ###
`LOAD(fpath${,dlg%})`  
Returns the text contained in the file at `fpath$` as a single string. The file at
`fpath$` must be either a TXT or PRG, or an error will occur.
The resource prefix must take the form `TXT:`.
- - -
`LOAD fpath${,dlg%} OUT var$`   
Same as above, but in `OUT` syntax. The string variable `var$` will take
the text of the file as its value.
