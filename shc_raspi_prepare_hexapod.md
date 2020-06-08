# 9. Preparing the Hexapod

[Previous: Enabling SSH](shc_raspi_enable_ssh.md)

Before launching the SHC launch files, you have to follow these steps with the hexapod.

9.1 Connect the dynamixel motors in your hexapod appropriately using suitable wires and hubs (TTL 3 pin wires for AX-12A motors).

![dynamixel_motor](media/dynamixel_motor.jpg "Dynamixel Motor and Cable")

9.2 Connect the TTL to USB dynamixel converter to your hexapod.

![dynamixel_converter](media/dynamixel_converter.jpg "TTL to USB Dynamixel Converters")

9.3 Connect power to the motors by using a suitable 12V power source like a Li-Po battery with a switch and a hub (Don't turn on the switch).

![lipo_battery](media/lipo_battery.jpg "Lipo Battery") ![dynamixel_hub](media/dynamixel_hub.jpg "Dynamixel Hubs")

9.4 Connect power to the Raspberry Pi using the same battery and switch and use a 5V regulator with sufficient current capacity (2.5A or more) with a micro USB adapter in between the battery and the Raspberry Pi.

![regulator](media/regulator.jpg "5V Regulator and Micro USB Adapter")

9.5 Plug the joystick into the Raspberry Pi using a USB port.

![joystick](media/joystick.jpg "Logitech Joystick")

9.6 Plug the TTL to USB dynamixel converter into the Raspberry Pi.

9.7 Modify the Syropod configuration file (syropod.yaml) according to the hexapod parameters. The important parameters are the DH parameters of the hexapod links, body clearance (height from the floor to the body), desired leg stance positions. See [SHC config](https://github.com/csiro-robotics/syropod_highlevel_controller/tree/master/config) for more information.

9.8 Modify the motor configuration file (syropod_motors.yaml) such that the motor IDs of the actual motors match with the desired convention. You can check the IDs of motors in the Dynamixel Wizard tool available on its own or as part of the RoboPlus software from Robotis.

![hexapod_body](media/hexapod_body.jpg "Hexapod before assembling") ![hexapody_assembled_raspi](media/hexapod_assembled_raspi.jpg "Hexapod after assembling")

[Next: Launching SHC](shc_raspi_launch_shc.md)

