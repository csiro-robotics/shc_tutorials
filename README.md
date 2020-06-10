# OpenSHC Tutorials

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

## How to use OpenSHC

OpenSHC is a versatile controller capable of generating body poses and gaits for quasi-static multilegged robots. This ROS package implemented in C++ can be easily deployed on legged robots with different sensor, leg and joint configurations. OpenSHC is designed to generate foot tip trajectories for a given gait sequence, step clearance, step frequency and input body velocity. Input sensors such as IMU and joint effort feedback can be utilised by the controller to provide robust trajectories even in inclined and uneven terrain. 

OpenSHC can be used to control simulated legged robots in RViz or Gazebo as well as real hardware implemented robots. The following tutorials will help to install and use OpenSHC to control legged robots both in simulation and real hardware. The code is available at [Syropod Highlevel Controller](https://github.com/csiro-robotics/syropod_highlevel_controller).

1. [Implementing OpenSHC on a PC](shc_pc.md)
2. [Implementing OpenSHC on a Raspberry Pi 3](shc_raspi.md)
3. [Implementing OpenSHC on a Raspberry Pi 4](shc_raspi4.md)
4. [Troubleshooting](troubleshooting.md)

[![Gizmo Wizmo Zero](https://i.imgur.com/HCrmRDS.gif "CSIRO Syropods")](https://research.csiro.au/robotics/our-work/research-areas/legged-robots/)

## Authors

* Oshada Jayasinghe
* Marisa Bucolo
* Benjamin Tam
* Navinda Kottege
