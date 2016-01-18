# System Variables #
SmileBASIC contains a set of system-reserved variables, which allow access to certain system-state
function at runtime.
The function of these variables depends on the variable itself, so they will be documented here.

## CALLIDX ##
Read-only. Tells the management number of the currently-executing callback.

## CSRX ##
Read-only. Tells the current x-coordinate of the print cursor.

## CSRY ##
Read-only. Tells the current y-coordinate of the print cursor.

## CSRZ ##
Read-only. Tells the current z-coordinate of the print cursor.

## DATE$ ##
Read-only. Date string in the format `YYYY/MM/DD` that tells the current system date.

## ERRLINE ##
Read-only. Line number of the source code where the last error occurred.

## ERRNUM ##
Read-only. Error number of the last error that occurred (see error table.)

## ERRPRG ##
Read-only. Slot number in which the last error occurred.

## FALSE ##
Read-only. Always 0.

## FREEMEM ##
Read-only. Amount of user memory that is currently free, in bytes.

## HARDWARE ##
Read-only. 0 if the system is an original 3DS, 1 if it is a New 3DS.

## MAINCNT ##
Read-only. Amount of time passed since SmileBASIC started, in frames.

## MICPOS ##
Read-only. Tells current sampling position within the microphone buffer.

## MICSIZE ##
Read-only. Number of samples to be stored within the microphone sample buffer.

## MPCOUNT ##
Read-only. Number of systems connected during wireless play.

## MPHOST ##
Read-only. Multiplayer ID of the host system.

## MPLOCAL ##
Read-only. Multiplayer ID of this system.

## PRGSLOT ##
Read-only. Tells the `PRG` slot currently being affected by `PRG` instructions.

## RESULT ##
Read-only. Tells the result of the last `SAVE`, `LOAD`, `DELETE`, or `DIALOG` instruction.
Value is dependent on instruction.

## SYSBEEP ##
Read/Write. If 0, system sound effects are disabled. If 1, system sounds are enabled.

## TABSTEP ##
Read/Write. Tells the number of spaces to put between `,` separated expressions in `PRINT`.
Valid range 0 - 16.

## TIME$ ##
Read-only. A time string in the format `HH:MM:SS` representing the current system time, in 24-hour.

## TRUE ##
Read-only. Always 1.

## VERSION ##
Read-only. An integer in the form `&HXXYYZZZZ` telling the current system version.
The `ZZZZ` portion appears to be little-endian, thus supporting tertiary versions up to 65535.   
In 3.2.1, it was `&H03020100`.
