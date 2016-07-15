# RINGCOPY #
Copy data between numeric arrays as if they were ring buffers.

## Description ##
`RINGCOPY` copies the contents of one linear (1D) numeric array to another, in order.
However, if the length of the destination array exceeds that of the source,
the contents of the source array are repeated to fill the destination.
In this way, the source array is treated as a ring buffer.
If the length of both arrays is equal, the result is equivalent to `COPY`.

## Differences from COPY ##
`RINGCOPY` has a number of differences from `COPY`.
They will be listed below.
- Copy destination offset is a required argument
- Running out of source data doesn't throw error (ring buffer copying, see above)
- No copying between string arrays (throws `Type mismatch`)
- No copying from a `DATA` label
- No copying characters between strings (throws `Type mismatch`)
- 2D arrays are treated as multichannel data instead of being linearized (see below)
- 3D and 4D arrays are unsupported (throws `Type mismatch`)
- Function form (see below)

### Multichannel Copying ###
If the output is a two-dimensional array, then it is treated
as multichannel data, with as many channels as the first dimension of
the array.

For example, a 2x5 array filled with zeroes may be modelled like this:

    +---+---+---+---+---+
    | 0 | 0 | 0 | 0 | 0 |
    +---+---+---+---+---+
    | 0 | 0 | 0 | 0 | 0 |
    +---+---+---+---+---+

When `RINGCOPY` sees this array, it treats each row as a separate "channel",
as if it were its own linear array.

    Channel 0
    +---+---+---+---+---+
    | 0 | 0 | 0 | 0 | 0 |
    +---+---+---+---+---+
    
    Channel 1
    +---+---+---+---+---+
    | 0 | 0 | 0 | 0 | 0 |
    +---+---+---+---+---+

