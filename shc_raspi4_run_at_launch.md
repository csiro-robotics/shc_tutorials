# 6. OPTIONAL: Setting Up SHC to Run at Launch

[Previous: Configuring The Wireless Access Point](shc_raspi4_configure_AP.md)

This step is optional. The instructions below outline enabling the robot to launch SHC and prepare to walk on startup rather than requiring manual activation and are adapted from this [article](https://risc.readthedocs.io/2-auto-service-start-afer-boot.html)

6.1 Create a folder in which to store your launch script, then create a launch script and make it executable

```bash
mkdir ~/launch_script
cd ~/launch_script
touch robot_launch.sh
chmod +x robot_launch.sh
```

6.2 Open the robot_launch file with a text editor of your choice and insert the following. Replace bracketed parameters with the value relevant to your system.

```bash
#!/bin/bash
source /opt/ros/[ROS VERSION]/setup.bash
source /home/[USERNAME]/openshc_ws/devel/setup.bash
roslaunch [ROS PACKAGE NAME] [LAUNCH FILE NAME].launch
```

6.3 Next you will need to create a systemd service file to run the bash script

```bash
cd /lib/systemd/system
sudo nano robot_launch.service
```

Then add the following into that file, replacing [USERNAME] with your username

```ini
[Unit]
Description=startup

[Service]
Type=forking
ExecStart=/home/[USERNAME]/launch_script/robot_launch.sh
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

6.4 Run the following commands to reload and enable the service

```bash
sudo systemtcl daemon-relaod
sudo systemctl enable robot_launch.service
```

6.5 Reboot the robot and check that the script activated by typing

```bash
rostopic list
```

into the terminal. If the list is not empty the script should run as expected when it receives controller input.

[Next: Launching SHC](shc_raspi4_launch.md)
