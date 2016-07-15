# Turns out I totally misunderstood RINGCOPY, and this document has it backwards :'( Don't read this for the time being #
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
- Return form (see below)

### Multichannel Copying ###
If the output is a two-dimensional array, then it is treated
as multichannel data, with as many channels as the first dimension of
the array. This differs from `COPY`, which treats arrays of higher
dimensions as if they were linear arrays, laid out as they are in memory.

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

In this mode, `RINGCOPY` can accept either a one-dimension or two-dimension array as input.

#### 1D Case ####
If the input array is one-dimensional, the input data is copied into each destination channel,
in the same ring buffer copying style as normal. In other words, it is treated
as if the input array has one channel (a 2D array whose first dimension is 1.)

    Destination
    Channel 0
    +---+---+---+---+---+
    | 1 | 2 | 3 | 1 | 2 | <-\   Source
    +---+---+---+---+---+   |   +---+---+---+
    Channel 1               +-< | 1 | 2 | 3 |
    +---+---+---+---+---+   |   +---+---+---+
    | 1 | 2 | 3 | 1 | 2 | <-/
    +---+---+---+---+---+

#### 2D Case ####
If the input array is two-dimensional, it is also treated as multichannel data.
The number of channels in the input (the first dimension) must match that of the output,
**with one exception:** if the input has a first dimension of 1 (one channel), the copy
is the same as the 1D case. The size of the second dimension need not match the destination.

The contents of each channel are copied from the source to the destination,
per channel. The contents of the first source channel are copied to
the first destination channel, and so on.

    Destination                 Source
    Channel 0                   Channel 0
    +---+---+---+---+---+       +---+---+---+
    | 1 | 2 | 3 | 1 | 2 | <---< | 1 | 2 | 3 |
    +---+---+---+---+---+       +---+---+---+
    Channel 1                   Channel 1
    +---+---+---+---+---+       +---+---+---+
    | 4 | 5 | 6 | 4 | 5 | <---< | 4 | 5 | 6 |
    +---+---+---+---+---+       +---+---+---+

If the destination is a linear array, a 2D array may not be used as source,
with the exception of 2D arrays with one channel (as described above).
In this case, the result is the same as copying between two linear arrays.
If the destination is a 2D array of one channel, it is also treated as if it
is linear.

Considering all edge cases of single-channel data, it can be thought that
`RINGCOPY` treats linear arrays as special cases of multichannel data,
where the arrays only contain one channel.

## Syntax ##
### Command ###
`RINGCOPY dest[],dofs%,src[]{{,sofs%},amount%}`  
Performs a ring buffer copy of the data from `src[]` to `dest[]`.
The data is written to `dest[]` starting at index `dofs%`.
All operations are performed per-channel. The source channel is treated
as a ring buffer.  
If `amount%` is passed, then only `amount%` items will be
copied. If `amount%` exceeds the length of the destination channel minus `dofs%`,
an error will occur.  
If `sofs%` is passed, then the copy will start at index `sofs%` of the source channel.
