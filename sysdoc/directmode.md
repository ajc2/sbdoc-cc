# DIRECT Mode #
**DIRECT Mode** is the command line provided within the SmileBASIC environment.
It is accessed by touching the DIRECT key on the keyboard when within the editor.  
The command line allows you to type in and execute any valid SmileBASIC code.  
In addition to this functionality, DIRECT mode exposes a number of differences from
a SmileBASIC program.

## Specific Features ##
DIRECT mode has a set of instructions that are only legal within it. These are:
- Changing the current active project of the editor with `PROJECT`
  - For example, `PROJECT "HELLO"` will set the editor's active project to `HELLO`
  - Note that this is different from the Change Active Project setting, which sets
    the default active project at start-up.
- Resetting the memory with `CLEAR`
- Clearing editor slots with `NEW`
  - `NEW` clears all slots, while `NEW slotnum%` clears only the specified slot.
- Run the program in a slot with `RUN`
  - If a slot number is not passed with `RUN`, it runs slot 0
  - This is the same behavior as pressing START or SELECT
- Jump to a line in the editor with `LIST`
- Check the call stack with `BACKTRACE`
- Continue a stopped program with `CONT`
