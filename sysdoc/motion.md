# Motion Sensors #
SmileBASIC is capable of utilizing the motion sensors in the 3DS.
These sensors can detect rotation of the system, acceleration,
or even the direction of gravity.

## Setting-up the sensors ##
The motion sensors must first be turned on with `XON MOTION`. The user
is first prompted with a non-closeable warning dialog telling them the
sensors will be activated. The keyboard's MOT light will also turn on.
Afterwards, the sensors are ready for use. They are all initialized to
their default states, using the current orientation as reference.

## Calibrating and resetting ##
The `GYROSYNC` instruction resets the gyro sensors to their default state.
Beyond this, there are no specific tools for calibration. Calibration
procedures must be set up by the programmer if necessary.

## Getting motion information ##
### Rotation ###
The angle of rotation of the system about its three axes can be obtained
with the `GYROA` instruction. `GYROA OUT pitch#,roll#,yaw#` loads the variables
`pitch#`,`roll#`, and `yaw#` with their respective angles. **Pitch** is rotation
about the x-axis, **roll** is about the y-axis, and **yaw** is about the z-axis.
The returned angles are measured in radians.

The **angular velocity** (that is, the speed at which the system is rotating) is
obtained by the `GYROV` instruction. `GYROV OUT pitch#,roll#,yaw#` returns the angular
velocity about the respective axis. The velocity is measured in radians per second.
