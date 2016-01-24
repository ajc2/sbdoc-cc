# SMILE Button #
The **SMILE Button** is a special key on the SmileBASIC keyboard. When pressed,
the SMILE Button launches a program specified by the user. This is useful
for developers who wish to use certain custom toolkits while in DIRECT mode.  
The SMILE Button is disabled while a program is running. By default, the assigned
program is `SYS/PRG:SMILETOOL`.

## Mapping the Button ##
The program mapped to the SMILE Button is chosen via the Options menu.
Simply select the Assign Program to SMILE Button option and navigate the file
viewer to select which program you wish to map.
Any valid `TXT` or `PRG` can be chosen.

## The Tool Slot ##
The **tool slot** refers to the hidden system slot that the currently mapped
program is loaded inside; the name is in reference to the built-in SmileTool program.
Internally, this slot is referred to as slot 4.  
A program executed from the SMILE Button can exploit certain behaviors that differ from
executing from a normal slot; such programs are called **tool programs**.  
These unique behaviors are listed below. Aside from these behaviors, launching from
the SMILE Button is the same as launching from the Viewer.
- Access to other project folders (see below)
- `PRGNAME$` for the current slot is the empty string
- If `EXEC` is used to launch a different slot,
execution will not return to the tool slot when `END` is encountered.
- `STOP` functions the same as `END`
- `COMMON DEF` is illegal
