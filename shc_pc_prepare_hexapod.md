# 5. Preparing the Legged Robot

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Previous: Simulating in Gazebo Simulation Environment](shc_pc_gazebo_simulation.md)

Before launching the OpenSHC launch files, you have to follow these steps with the legged robot. Here we are using a slightly modified [Trossen Robotics PhantomX mk 1 hexapod robot](https://www.trossenrobotics.com/phantomx-ax-hexapod-mk1.aspx). The following image shows the robot before connecting the servo cables to the hub.

![hexapod_body](media/hexapod_body.jpg "Hexapod before assembling")

5.1 Connect the dynamixel motors of the robot appropriately using the suitable cables and hubs (TTL 3 pin cables for AX-12A motors).

![dynamixel_motor](media/dynamixel_motor.jpg "Dynamixel Motor and Cable")

5.2 Connect a [USB2Dynamixel converter](https://www.trossenrobotics.com/robotis-bioloid-usb2dynamixel.aspx) or an equivalent converter such as the [USB2ax converter](https://www.seeedstudio.com/USB2AX-p-1349.html) that converts from TTL (or RS485 if you are using different series of Dynamixel servos) to USB to your robot.

![dynamixel_converter](media/dynamixel_converter.jpg "TTL to USB Dynamixel Converters")

5.3 Connect power to the motors by using a suitable power source (e.g: 3 cell Li-Po battery or 12V power supply with sufficient current output) with a switch and a hub (Don't turn on the switch). 

![lipo_battery](media/lipo_battery.jpg "Lipo Battery") ![dynamixel_hub](media/dynamixel_hub.jpg "Dynamixel Hubs")

The following image shows the modified hexapod robot with the cables connected.

 ![hexapody_assembled](media/hexapod_assembled.jpg "Hexapod after assembling")

5.4 Plug a gamepad controller into your machine such as the [Logitech F710 Wireless Gamepad](https://www.logitechg.com/en-au/products/gamepads/f710-wireless-gamepad.940-000119.html) for control. Other gamepads may be used, but the mapping may differ.

![joystick](media/joystick.jpg "Logitech Joystick")

5.5 Plug the USB2Dynamixel converter into your machine. It is better to use a long USB extension cable such that the hexapod has space to operate.

![usb_extension](media/usb_extension.jpg "USB Extension Cable")

5.6 Modify the Syropod configuration file (syropod.yaml) according to the legged robot parameters. The important parameters are the [Denavit-Hartenberg (DH) parameters](https://en.wikipedia.org/wiki/Denavit%E2%80%93Hartenberg_parameters) of the robot's leg links, body clearance (height from the floor to the body), desired leg stance positions. See [SHC config](https://github.com/csiro-robotics/syropod_highlevel_controller/tree/master/config) for more information.

5.7 Modify the motor configuration file (syropod_motors.yaml) such that the motor IDs of the actual motors match with the desired convention. You can check the IDs of motors by the tool [Dynamixel Wizard](https://emanual.robotis.com/docs/en/software/rplus1/dynamixel_wizard/) in [RoboPlus software by Robotis](http://www.robotis.us/roboplus-r-educational-software-apps/).


[Next: Launching OpenSHC](shc_pc_launch_shc.md)
