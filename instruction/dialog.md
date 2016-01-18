# DIALOG #
Generate a special dialog on the Touch Screen, optionally accepting user input.

## Use ##
`DIALOG(text$[,type%[,caption$[,timeout%]]])`  
Display a dialog on the Touch Screen. The dialog will show the contents of `text$`.
The text of a dialog is different from the text on the console (see notes.)  
The integer `type%` controls what input type the dialog will have.
The function returns a value based on the user input (see notes.)  
`caption$` is the text displayed on the dialog's caption bar. If not passed,
it is assumed to be the empty string.  
`timeout%` sets the amount of time until the dialog automatically closes.
If it is positive, the time is taken in seconds. If it is negative, it is taken in frames.
If `timeout%` is not passed it is assumed to be zero.
- - -
`DIALOG text$[,type%[,caption$[,timeout%]]] OUT outvar%`  
Same as above, but written as an `OUT` instruction. The return value is written to `outvar%`.
- - -
`DIALOG text$[,type%[,caption$[,timeout%]]]`  
Same, but written as a command. If using a button input type, 
it is impossible to get the return value from this format (see notes.)
- - -
`DIALOG(init$,caption$[,maxchars%])`  
Creates a filename keyboard dialog on the Touch Screen (see notes.)  
`init$` is the placeholder string within the input field when the dialog opens.
If `init$` exceeds the length given in `maxchars%`, it is trimmed to fit.  
`caption$` is the caption bar text.  
`maxchars%` sets the limit on how many characters maximum can be entered in the input field.
The value of `maxchars%` must be at least 1 and at most 14.

## Examples ##
`DIALOG "Hello world!"`  
Creates a dialog on the Touch Screen that reads `Hello world!` and has an OK button.
- - -
`DIALOG "Ready to execute?",4`  
Creates a dialog with Cancel/Run buttons.
- - -
`PRINT DIALOG("Press a button within 5 seconds!",-15,"ALERT",5)`
Creates a button input dialog that times out in 5 seconds. The return value is printed.

## Notes ##
### Input Types and Return Values ###
Dialogs have a number of input types that control their function as well as their return value.
If the input type is non-negative, the dialog uses a "selection" type. The selection depends on the type value passed.
- 0: OK
- 1: No/Yes
- 2: Back/Next
- 3: Cancel/OK
- 4: Cancel/Run
- 5: Next

