# LOAD #
Instructions for loading files.

## Use ##
`LOAD fname$[,diag%]`  
Loads the file `fname$`. How it is loaded depends on the type prefix.  
- `PRG:` or none: the file is loaded as a `PRG` in the current slot.
- `PRG%:`, where `%` is a slot number: the file is loaded as a `PRG` in the given slot.
- `GRP%:`, where `%` is a graphic page number: the file is loaded as a `GRP` in the given graphic page.
- `GRPF:` the file is loaded as a `GRP` to the font graphic page.

In a tool slot, it is legal to specify a project name before the file name to load files from other projects.
Loading from the `SYS` project is legal from any slot.  
If `diag%` is zero, the load confirmation dialog will not appear.
If `diag%` is non-zero or not passed, it will.  
The use of `diag%` is the same for all versions of `LOAD`.
- - -
`LOAD fname$[,diag%] OUT stringvar$`  
The contents of `fname$` are loaded to `stringvar$` as a single string.  
The file at `fname$` must be a `TXT` file.  
`PRG` can be loaded as well as they are interoperable,
but the type prefix of `fname$` must be `TXT:` anyway.
- - -
`LOAD(fname$[,diag%])`  
Returns the contents of `fname$` as a single string. Loading rules are the same as above.
- - -
`LOAD fname$,numarr[,diag%]`  
Loads the contents of `fname$` into the numeric array `numarr`.
The file at `fname$`must be a `DAT` file. GRP files are not interoperable,
so you cannot load a `GRP` to an array with this method, even if you use the `DAT:` type prefix.  
It is impossible to create text `DAT` files, so passing a string array is illegal.
