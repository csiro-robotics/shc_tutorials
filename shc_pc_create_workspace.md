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

3.3 Clone the Hexapod package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/frankenX_syropod.git
```

3.4 Clone the Syropod High Level Controller package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/syropod_highlevel_controller.git
```

3.5 Clone the Syropod Remote package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/syropod_remote.git
```

3.6 Clone the Dynamixel Motor package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/dynamixel_motor.git
```

3.7 Clone the Dynamixel Joint State Publisher package to the src folder in your workspace by,

```bash
git clone https://github.com/csiro-robotics/dynamixel_joint_state_publisher.git
```

3.8 Open your workspace

```bash
cd ~/openshc_ws
```

3.9 Compile your workspace by

```bash
catkin build
```

3.10 Make sure the catkin workspace is successfully compiled and source the devel/setup.bash file from your workspace.

```bash
source ~/openshc_ws/devel/setup.bash
```

3.11 You have to source the devel/setup.bash file for each terminal session you want to use SHC. You can edit the .bashrc file to get it automatically sourced to each terminal session. Open the .bashrc file by,

```bash
nano ~/.bashrc
```

3.12 Add the following line to the end of the file and save it.

```bash
source ~/openshc_ws/devel/setup.bash
```

3.13 See [Troubleshooting](troubleshooting.md) if you encounter with any problems.

[Next: Simulating in Gazebo Simulation Environment](shc_pc_gazebo_simulation.md)
