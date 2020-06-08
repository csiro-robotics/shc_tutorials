# 3. Configuring the Catkin Workspace

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Previous: Booting the Pi for the First Time](shc_raspi4_boot.md)

After installing ROS and other required packages, a catkin workspace should be created including the required ROS packages. You can visit [Installing and Configuring Your ROS Environment](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) to see more details. As this image was created with a specific project in mind you will first need to remove the original catkin workspace to proceed. DO NOT REMOVE ROS_CATKIN_WS. This is the folder containing your Melodic install, not a standard catkin_ws.

5.0 To be able to install relevant packages you will need to update package lists. As this image was created some time ago the date will be wrong so this also needs to be changed. The date used below is an example only.

``` bash
sudo date -s "20 JAN 2020 15:30:25"
sudo apt-get update
```

5.1 Remove existing catkin_ws

```bash
rm -r ~/catkin_ws
```

5.2 Create a catkin workspace including the src folder in your home directory by,

```bash
mkdir -p ~/openshc_ws/src
# Here openshc_ws is the name given to the catkin workspace. You can use any other name you wish.
```

5.3 Open the src folder in the created workspace

```bash
cd ~/openshc_ws/src
```

5.4 Install catkin_tools for greater control over ROS build parameters

```bash
sudo apt-get install python-catkin-tools
```

5.3 Clone the legged robot package to the src folder in your workspace. Alternatively, use a custom package for your legged robot

```bash
git clone https://github.com/csiro-robotics/frankenX_syropod.git
```

5.4 Clone the Syropod High Level Controller package to the src folder in your workspace.

```bash
git clone https://github.com/csiro-robotics/syropod_highlevel_controller.git
```

5.5 Clone the Syropod Remote package to the src folder in your workspace

```bash
git clone https://github.com/csiro-robotics/syropod_remote.git
```

5.6 Clone the Dynamixel Motor package to the src folder in your workspace.

```bash
git clone https://github.com/csiro-robotics/dynamixel_motor.git
git clone https://github.com/csiro-robotics/dynamixel_joint_state_publisher.git
```

5.7 Clone the ROS joystick drivers. This is a meta-package of which you only require the "joy" package found inside. Copy this "joy" package into the main src folder and delete the rest of the joystick drivers metapackage. This can be done in terminal but is easiest using Raspian's file explorer GUI

```bash
git clone https://github.com/ros-drivers/joystick_drivers.git
```

[Next: Compiling the Catkin Workspace](shc_raspi4_compile_workspace.md)
