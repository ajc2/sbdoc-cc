# GOFS #
Move the GRP layer around the screen.

***This instruction is only available in version 3.3.0.*  
This version is currently only available in Japan,
so this feature will throw an error upon use in other regions.**

## Syntax ##
### Setting the Offset ###
`GOFS x%,y%`  
Offset the GRP layer by `x%` and `y%`.  
The GRP layer's upper-left corner will be placed at `x%,y%`.
Negative values are allowed.

### Getting the Offset ###
`GOFS OUT xvar%,yvar%`  
Gets the offset coordinates of the GRP layer.  
`xvar%` and `yvar%` take the x and y values repsectively.

## Examples ##
`GOFS 10,20`  
The GRP layer's upper-left corner will be at 10,20.
- - -
```
GOFS OUT X%,Y%
PRINT X%,Y%
```
Prints the GRP's offset coordinates.
