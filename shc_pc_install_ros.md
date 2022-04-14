# 1. Installing ROS

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Back to Implementing OpenSHC on a PC](shc_pc.md)

The first step of implementing OpenSHC is to install ROS Noetic on your Ubuntu 20.04 LTS System or ROS Melodic on your Ubuntu 18.04 LTS System by the following terminal commands. You can visit [Ubuntu install of ROS Noetic](http://wiki.ros.org/noetic/Installation/Ubuntu) to see a detailed guide on how to install ROS Noetic, or [Ubuntu install of ROS Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu) for ROS Melodic.


1.1 First setup your sources.list by,

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

1.2 Then setup your keys by,

```bash
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

1.3 Make sure your debian packages are up to date by,

```bash
sudo apt update
```

1.4 Install the full version of ROS Noetic by,

```bash
sudo apt install ros-noetic-desktop-full
```
or if using ROS Melodic:
```bash
sudo apt install ros-melodic-desktop-full
```


1.5 Before using ROS, install useful build tools and dependencies by the following commands.

```bash
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
sudo rosdep init
rosdep update
```

1.6 You can enable ROS on your current shell by,

```bash
source /opt/ros/$ROS_DISTR/setup.bash
```

1.7 However it is convenient to source the setup.bash file to every shell. You can do this by editing the .bashrc file in your system. Open the .bashrc file by,

```bash
nano ~/.bashrc
```

1.8 Then add the following line to the end of the file and save it.

```bash
source /opt/ros/$ROS_DISTR/setup.bash
```

* If you are using Anaconda please comment the line `export PATH=/USER/anaconda3/bin:$PATH` (can be slightly different to this) if it is shown in the .bashrc file at the same time because it can cause confusions with ROS.

1.9 Finally check whether you have successfully installed ROS by starting roscore. It should start ROS without getting any error messages.

```bash
roscore
```


[Next: Installing Other Required Packages](shc_pc_install_other.md)
