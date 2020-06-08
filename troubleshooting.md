# Troubleshooting

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Back to the main page](README.md)

---

**Problem:** When launching SHC, you get an error saying, "could not open port: No such file or directory".

**Solution:** You have to modify the "port name" parameter in the dynamixel_controller_manager.launch file in the launch folder of the syropod package. You can identify the relevant port by running,

```bash
  ls /dev/tty*
```

in the terminal for the two occasions the USB dynamixel converter is plugged in and plugged out. (Usually something like ttyUSB0 or ttyACM0) Modify the launch file, save it and run the launch file again.

---

**Problem:** When launching SHC, you get an error saying, "could not open port: Device or resource busy".

**Solution:** Wait for some time and run the launch file again. If you are running the CSIRO Pi Hat this can be a sign that bluetooth was not disabled correctly, check you've followed all steps and try again.

---

**Problem:** When compiling the workspace, you get an error saying, "Permission denied".

**Solution:** Run the following commands to give execute permissions to the required files. (There may be files requiring permission in addition to the following)

```bash
  sudo chmod +x ~/openshc_ws/src/dynamixel_motor/dynamixel_controllers/nodes/controller_manager.py
  sudo chmod +x ~/openshc_ws/src/dynamixel_motor/dynamixel_controllers/nodes/controller_spawner.py
  sudo chmod +x ~/openshc_ws/src/dynamixel_joint_state_publisher/nodes/joint_states_publisher.py
```

---

**Problem:** When launching SHC, the robot movements are pretty slow and the robot seems to struggle.

**Solution:** Check the frequency of the state and command topics of joints by running the following two commands in the terminal and make sure they are in a similar range. (Ex:- 50Hz and 47Hz)

```bash
  rostopic hz /syropod/AR_coxa_joint/state
  rostopic hz /syropod/AR_coxa_joint/command
```

---

**Problem:** The frequencies of the state and command topics of joints are significantly different.

**Solution:** Open the dynamixel python driver by,

```bash
  nano ~/openshc_ws/src/dynamixel_motor/dynamixel_driver/src/dynamixel_driver/dynamixel_io.py
```

Check the value in time.sleep function under ping, read and write functions and if it is higher than 0.0005, set it to 0.0005.

* Make sure you run `sudo setserial /dev/ttyACM0 low_latency` if you are using a Raspberry Pi as well.

---

**Problem:** It takes so much time or fails to compile the catkin workspace when using a Raspberry Pi.

**Solution:** Make sure you use single threading compiling with -j1 argument and you have created a swapfile of 4GB. Since Raspberry Pi has limited resources it is normal to take around one hour for compiling the workspace.

---

**Problem:** Is there a way to launch the files on startup without using a display or SSH?

**Solution:** See the following page on running SHC at launch [here](shc_raspi4_run_at_launch.md)

---

[Back to the main page](README.md)

