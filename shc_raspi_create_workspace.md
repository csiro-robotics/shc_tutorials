# 5. Creating the Catkin Workspace

[Previous: Installing Other Required Packages](shc_raspi_install_other.md)

After installing ROS and other required packages, a catkin workspace should be created including the required ROS packages. You can visit [Installing and Configuring Your ROS Environment](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) to see more details.

5.1 Create a catkin workspace including the src folder in your home directory by,

```bash
mkdir -p ~/openshc_ws/src
# Here openshc_ws is the name given to the catkin workspace. You can use any other name as you wish.
```

5.2 Open the src folder in the created workspace by,

```bash
cd ~/openshc_ws/src
```

5.3 Clone the Hexapod package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/frankenX_syropod.git
```

5.4 Clone the Syropod High Level Controller package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/syropod_highlevel_controller.git
```

5.5 Clone the Syropod Remote package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/syropod_remote.git
```

5.6 Clone the Dynamixel Motor package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/dynamixel_motor.git
```

5.7 Clone the Dynamixel Joint State Publisher package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/dynamixel_joint_state_publisher.git
```

[Next: Compiling the Catkin Workspace](shc_raspi_compile_workspace.md)
