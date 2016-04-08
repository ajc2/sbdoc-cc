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

### Loading Numeric Arrays (DAT) ###
`LOAD fpath$,out[]{,dlg%}`   
Loads the DAT file at `fpath$` as a numeric array, storing the contents in `out[]`.  
`out[]` must be the same dimensions and size as the DAT file at `fpath$`, or an error
will occur. An exception to this rule is in the case of linear arrays, in which case
`out[]` will resize to fit the contents of the file.  
`out[]` must be a numeric array; string DATs cannot be created,
so passing a string array is illegal.  
The resource prefix must take the form `DAT:`.
#### Loading GRPs as DAT ####
If the file at `fpath$` is a GRP, its contents can be loaded as a numeric array.
This is a useful shortcut if only the raw image data of the GRP is immediately needed.  
`out[]` must be a 2-dimension numeric array of any size. Upon load, it will contain
the raw image data of the GRP in 16-bit RGBA5551 color format. `out[]` will automatically be
resized to 512x512, regardless of its starting size.
The color data of a pixel (x,y) corresponds to the array index `out[y,x]`.

### Loading Graphic Pages (GRP) ###
`LOAD fpath${,ox%,oy%}{,dlg%}`   
The GRP file at `fpath$` will be loaded to the given graphic page, at the optionally given offset.  
The resource prefix must take the following form:
- `GRP%:`, where `%` is a valid GRP page number (0-5)
- `GRPF:` - The given GRP file is loaded as font graphics to the font page (-1).

If `ox%` and `oy%` are passed, the GRP image will be written to the graphic page
starting with the image's upper-left corner at the pixel (ox%,oy%). Negative values are also valid.
