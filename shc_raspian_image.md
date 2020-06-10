# 1. Installing Raspian Buster and ROS Melodic from a Prebuilt Image

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Back to Implementing OpenSHC on a Raspberry Pi 4](shc_raspi4.md)

The first step of implementing OpenSHC on a Raspberry Pi 4 is to flash a publicly available image of Raspian Buster which already has ROS Melodic installed. This saves a significant amount of time as ROS must be built from source on this Operating System. If you wish to create an image yourself there is a link to the image creator's instructions.

PLEASE NOTE: The creator of this image is not in any way affiliated with the CSIRO. As such CSIRO cannot guarantee these instructions will continue to be correct into the future. Please log a bug report if this guide is no longer accurate. Additionally, ROS packages from a source install cannot be acquired using apt, they will need to be downloaded as source and built as a standard ROS package.

Instructions used to produce the pi image are from [ROS Melodic on Raspberry Pi 4[Debian Buster] + RPLIDAR A1M8](https://www.instructables.com/id/ROS-Melodic-on-Raspberry-Pi-4-RPLIDAR/)

1.1 Download the prebuilt [image](https://drive.google.com/file/d/1lcPBYgdFG7EuaIV23B2-7tL10EMizMD9/view).

1.2 Download and install [Etcher](https://www.balena.io/etcher/). (You can use any other suitable software as well)

1.3 Obtain a micro-SD card. (32GB or above is recommended)

1.4 Select the extracted image file and flash it to the SD card using Etcher. See this [guide](https://www.raspberrypi.org/magpi/pi-sd-etcher/) for more information.

1.5 Remove the SD card from the computer.

1.6 Insert the SD card into the Raspberry Pi 4 micro SD slot located on the underside of the board at the opposite end to the USB ports.

[Next: Booting the Pi for the First Time](shc_raspi4_boot.md)
