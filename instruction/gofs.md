# GOFS #
Move the GRP layer around the screen.

## Use ##
`GOFS x%,y%`  
Offset the GRP layer by `x%` and `y%`.
- - -
`GOFS OUT xvar%,yvar%`  
Gets the offset coordinates of the GRP layer.
`xvar%` and `yvar%` take the x and y values repsectively.

## Examples ##
`GOFS 10,20`  
blegh
- - -
```
GOFS OUT X%,Y%
PRINT X%,Y%
```
Prints the GRP's offset coordinates.
