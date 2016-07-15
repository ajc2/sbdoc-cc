# RINGCOPY #
Copy data between numeric arrays as if they were ring buffers.

## Description ##
`RINGCOPY` copies the contents of one linear (1D) numeric array to another, in order.
However, if the length of the destination array exceeds that of the source,
the contents of the source array are repeated to fill the destination.
In this way, the source array is treated as a ring buffer.

### Multichannel Copying ###
If the input and output are two-dimensional arrays, they are treated
as multichannel data.
