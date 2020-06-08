# 4. Installing Other Required Packages

[Previous: Installing ROS](shc_raspi_install_ros.md)

The following packages should be installed in addition to ROS for the successful implementation of SHC.

4.1 Install ROS joystick, ROS control, ROS controllers, python catkin tools, python serial, setserial and wireless tools packages by,

```bash
sudo apt-get install ros-melodic-joy ros-melodic-ros-control ros-melodic-ros-controllers python-catkin-tools python-serial setserial wireless-tools
```

4.2 To save having to change permissions on your USB ports after every boot add your user to the dialout group as shown below

```bash
sudo usermod -a -G dialout $USER
```

You will need to reboot for the changes to take effect.

[Next: Creating the Catkin Workspace](shc_raspi_create_workspace.md)
