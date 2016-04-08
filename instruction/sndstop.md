# SNDSTOP #
Stops all sound that is currently playing.

***This instruction is only available in version 3.3.0.*  
This version is currently only available in Japan,
so this feature will throw an error upon use in other regions.**

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
Stops all sounds currently playing..
