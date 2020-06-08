# 10. Launching SHC

[Previous: Preparing the Hexapod](shc_raspi_prepare_hexapod.md)

After preparing the hexapod, you can launch the ROS launch files and implement SHC with the real hexapod.

10.1 Turn on the switch of the hexapod to turn on the motors and boot the Raspberry Pi.

10.2 Allow some time for the Raspberry Pi to boot and log on to your router or the mobile hotspot to find the ip-address of the Raspberry Pi.

10.3 SSH into the Raspberry Pi from your PC or laptop by,

```bash
ssh username@ip-address
```

* Here username should be the username of the Raspberry Pi (default is ubuntu) and ip-address should be the ip address of the Raspberry Pi obtained by the router or the mobile hotspot. (e.g. ssh ubuntu@192.168.1.1)

10.4 Enter your log in details and log in to the Raspberry Pi.

10.5 Source the devel/setup.bash file from your workspace if it is not added to the .bashrc file.

```bash
source ~/openshc_ws/devel/setup.bash
```

10.6 Set the latency of the dynamixel port to low by,

```bash
sudo setserial /dev/ttyACM0 low_latency
```

* ttyACM0 should be replaced with your matched port if necessary.

10.7 First launch the Syropod Hardware Controller launch file from the terminal by,

```bash
roslaunch frankenX_syropod frankenX_hardware.launch
```

10.9 Make sure that the all motors are identified with their relevant IDs and all controllers have been started.

10.10  kill the process by "CTRL+C" and launch both the Syropod Hardware Controller and the Syropod Highlevel Controller from the terminal at once by,

```bash
roslaunch frankenX_syropod frankenX_start.launch
```

10.11 The system is initially at suspended state.

![suspended_state](media/suspended_state.png "Suspended State")

10.12 Press the Logitech button after acquiring the robot state to change the system state to operational.

![operational_state](media/operational_state.png "Operational State")

10.13 Press the start button to change the robot state to ready state.

![ready_state](media/ready_state.png "Ready State")

10.14 Press the start button again to change the robot state to running state.

![running_state](media/running_state.png "Running State")

10.15 When the workspace is generated and the syropod is ready to walk you can control the hexapod from the joystick. Visit [How to Control the Hexapod](shc_guide_hexapod.md) to learn how to control the hexapod from the joystick.

[//]: # (Insert the embedded link of PhantomX implementation with Raspberry Pi.mp4 here)

10.16 See [Troubleshooting](troubleshooting.md) if you encounter with any problems.

[Back to Implementing SHC on a Raspberry Pi 3](shc_raspi.md)
