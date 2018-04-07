# Tuning

**ADVi3** includes tools to help you tune soma aspects of your printer.

### Extruder Tuning

![](assets/054_extruder_3.png)

In general, you only have to do this **once** except if you change radically your extruding temperature or if your environmental conditions change, such as humidity, or if you change the insulation on the heater block, such as switching to a silicone sock.

### PID Tuning

![](assets/058_pid_tuning_1.png)

In general, you only have to do this **once** except if you change radically your extruding temperature or if your environmental conditions change (such as humidity).

### XYZ motors Tuning

![](assets/056_motors.png)

In general, you only have to do this **once** because these parameters do not change with time. You have to redo this if you change the stepper motors or if you adjust the drivers current (on the mainboard).

## Manual leveling

![](assets/048_manual_leveling.png)

You only have to do this if you do not have a sensor (such as BLTouch).

You have to do this frequently (almost before each print) and it is sometimes difficult to level all the points if your bed or other parts, such as linear rods, are bent.

## Sensor Z-height

![](assets/106_z_height.png)

You only have to do this if you have a sensor (such as BLTouch).

You only have to do this from time to time especially if you move or disassemble parts such as the extruder.

## Sensor Bed Leveling

![](assets/102_sensor_grid.png)

You only have to do this if you have a sensor, such as the BLTouch. You can also do this, without displaying the grid, using the `G29` command either from a G-code start script or manual command.

## Reset Settings

![](assets/066_factory_reset.png)

If you reset settings, you will have to either perform the tunings again or reenter each of the settings.

## Flashing of new firmware version

If you flash a new firmware (especially a major version number), you may loose your settings and you have to either perform again the tunings or reenter the different settings.


