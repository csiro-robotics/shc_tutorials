# 3. Creating the Catkin Workspace

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Previous: Installing Other Required Packages](shc_pc_install_other.md)

After installing ROS a catkin workspace should be created including the required ROS packages. You can visit [Installing and Configuring Your ROS Environment](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) to see more details.

3.1 Create a catkin workspace including the src folder in your home directory by,

```bash
mkdir -p ~/openshc_ws/src
# Here openshc_ws is the name given to the catkin workspace. You can use any other name as you wish.
```

3.2 Open the src folder in the created workspace by,

```bash
cd ~/openshc_ws/src
```

3.3 Clone the Syropod High Level Controller package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/syropod_highlevel_controller.git
```

3.4 Clone the Syropod Remote package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/syropod_remote.git
```

3.5 Open your workspace

```bash
cd ~/openshc_ws
```

3.6 Compile your workspace by

```bash
catkin build
```

3.7 Make sure the catkin workspace is successfully compiled and source the devel/setup.bash file from your workspace.

```bash
source ~/openshc_ws/devel/setup.bash
```

3.8 You have to source the devel/setup.bash file for each terminal session you want to use OpenSHC. You can edit the .bashrc file to get it automatically sourced to each terminal session. Open the .bashrc file by,

```bash
nano ~/.bashrc
```

3.9 Add the following line to the end of the file and save it.

```bash
source ~/openshc_ws/devel/setup.bash
```

3.10 See [Troubleshooting](troubleshooting.md) if you encounter with any problems.

3.11 Syropod High Level Controller and Syropod Remote are the 2 core packages that run on every platform in simulation and hardware. The 3rd core package is platform specific parameters and configurations which is stored in the platform \<name\>_syropod package. If using OpenSHC with a Gazebo simulation, please skip to [Simulating in Gazebo Simulation Environment](shc_pc_gazebo_simulation.md). Else, for OpenSHC with the hexapod hardware robot platform frankenX_syropod, please continue on to 3.12.

3.12 Open the src folder in the created workspace by,

```bash
cd ~/openshc_ws/src
```

3.13 Clone the Hexapod package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/frankenX_syropod.git
```

3.14 Clone the Dynamixel Motor package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/dynamixel_motor.git
```

3.15 Clone the Dynamixel Joint State Publisher package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/dynamixel_joint_state_publisher.git
```

3.16 Repeat steps 3.5 to 3.7

3.17 Skip to [Preparing the Legged Robot](shc_pc_prepare_hexapod.md)

[Next: Simulating in Gazebo Simulation Environment](shc_pc_gazebo_simulation.md)
