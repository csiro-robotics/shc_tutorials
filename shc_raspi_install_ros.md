# 3. Installing ROS

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Previous: Booting the Raspberry Pi](shc_raspi_boot_raspi.md)

After booting the Raspberry Pi with a working internet connection, you can install ROS Melodic by following these steps. You can visit [Ubuntu install of ROS Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu) to see a detailed guide on how to install ROS Melodic.

3.1 First setup your sources.list by,

```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

3.2 Then setup your keys by,

```bash
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```

3.3 Make sure your debian packages are up to date by,

```bash
sudo apt update
```

3.4 Since Raspberry Pi has limited resources and Ubuntu Server 18.04 does not have a GUI, it is sufficient to install the desktop version of ROS Melodic by,

```bash
sudo apt install ros-melodic-desktop
```

3.5 Before using ROS, initialize ROS by the following two commands.

```bash
sudo rosdep init
rosdep update
```

3.6 You can enable ROS on your current shell by,

```bash
source /opt/ros/melodic/setup.bash
```

3.7 However it is convenient to source the setup.bash file to every shell. You can do this by editing the .bashrc file in your system. Open the .bashrc file by,

```bash
nano ~/.bashrc
```

3.8 Then add the following line to the end of the file and save it.

```bash
source /opt/ros/melodic/setup.bash
```

3.9 Finally check whether you have successfully installed ROS by starting roscore. It should start ROS without getting any error messages.

```bash
roscore
```

[Next: Installing Other Required Packages](shc_raspi_install_other.md)
