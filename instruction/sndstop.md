# SNDSTOP #
Stops all sound that is currently playing.

## Description ##
`SNDSTOP` immediately stops all sounds playing on the system.
It is equivalent to the following:

  BGMSTOP -1
  TALKSTOP
  EFCOFF
  PCMSTOP

In addition, `SNDSTOP` will stop all sound effects currently playing.

## Syntax ##
`SNDSTOP`  
Stops all sounds currently playing.

## Bugs ##
- Only stops the most recently-played sound effect.
