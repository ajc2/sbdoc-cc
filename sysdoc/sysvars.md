# System Variables #
SmileBASIC contains a set of system-reserved variables, which allow access to certain system-state
function at runtime.
The function of these variables depends on the variable itself, so they will be documented here.

|Variable|Access|Description                                                          |
|--------|------|---------------------------------------------------------------------|
|CALLIDX |  r   |Management number of the currently-executing callback.               |
|  CSRX  |  r   |Current x-coordinate of the print cursor.                            |
|  CSRY  |  r   |Current y-coordinate of the print cursor.                            |
|  CSRZ  |  r   |Current z-coordinate of the print cursor.                            |
|  DATE$ |  r   |Date string (`YYYY/MM/DD` form) of current system date.              |
|ERRLINE |  r   |Line number of the source code where the last error occurred.        |
| ERRNUM |  r   |Error number of the last error that occurred (see error table.)      |
| ERRPRG |  r   |Slot in which the last error occurred.                               |
| FALSE  |  r   |Always 0. Use `#FALSE` instead.                                      |
|FREEMEM |  r   |Current amount of free user memory, in bytes. Max memory 8MiB.       |
|HARDWARE|  r   |Tells the current system. 0 is 3DS, 1 is N3DS.                       |
|MAINCNT |  r   |Amount of time passed since SmileBASIC started, in frames.           |
| MICPOS |  r   |Current sampling position within the microphone buffer.              |
|MICSIZE |  r   |Number of samples to be stored within the microphone sample buffer.  |
|MPCOUNT |  r   |Number of systems connected during wireless play.                    |
| MPHOST |  r   |Multiplayer ID of the host system.                                   |
|MPLOCAL |  r   |Multiplayer ID of the current system.                                |
|PRGSLOT |  r   |`PRG` slot currently being affected by `PRG` instructions.           |
|RESULT  |  r   |Result of the last `SAVE`, `LOAD`, `DELETE`, or `DIALOG`.            |
|SYSBEEP |  rw  |If 0, system sound effects are disabled. If 1, they are enabled.     |
|TABSTEP |  rw  |Number of spaces put between `,`-separated expressions when printing.|
|  TIME$ |  r   |Time string (`HH:MM:SS` 24-hour form) of the current system time.    |
|  TRUE  |  r   |Always 1. Use `#TRUE` instead.                                       |
|VERSION |  r   |Current version `X.Y.Z` encoded as an integer, in `&HXXYYZZZZ` form. |
