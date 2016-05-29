# SNDSTOP #
Stops all sound that is currently playing.

***This is only available in version 3.3.0. and above.*  
If you plan on writing your program for compatibility with previous
versions, don't use this feature.**

## Description ##
`SNDSTOP` immediately stops all sounds playing on the system.
It is equivalent to the following:
```
BGMSTOP -1
TALKSTOP
PCMSTOP
```
In addition, `SNDSTOP` will stop all BEEPs currently playing.

## Syntax ##
`SNDSTOP`  
Stops all sounds currently playing.
