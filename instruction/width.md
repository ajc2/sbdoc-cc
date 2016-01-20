# WIDTH #
Set or get the console text scale.

## Use ##
`WIDTH setting%`  
Sets the console scale based on `setting%`. Only the following values are valid.
- 8: Console text is set at 8x8 (1x scale)
- 16: Console text is set at 16x16 (2x scale)

- - -
`WIDTH()`  
Returns the current console scale setting (either 8 or 16).
- - -
`WIDTH OUT outvar%`  
`outvar%` is set to the current console scale setting.

## Examples ##
`WIDTH 16`  
The console is set to 2x scale.

## Notes ##
Supposedly, `WIDTH` is intended to be an accessibility feature. Despite this,
its introduction led to regular use for large text graphics.
