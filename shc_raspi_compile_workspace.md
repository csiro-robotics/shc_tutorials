# 6. Compiling the Catkin Workspace

[Previous: Create the Catkin Workspace](shc_raspi_compile_workspace.md)

Since a Raspberry Pi has limited resources, the compiling of the Syropod Highlevel Controller (SHC) package requires to create a swapfile of 4GB to overcome insufficient memory.

6.1 Disable swapoff by,

```bash
sudo swapoff /swapfile
```

6.2 Delete the swapfile by,

```bash
sudo rm /swapfile
```

6.3 Create a new swapfile of 4GB by,

```bash
sudo fallocate -l 4G /swapfile
```

If fallocate is not installed you can instead use the command below however it is significantly slower.

```bash
sudo dd if=/dev/zero of=/swapfile bs=1M count=4096
```

6.4 Assign read/write permissions to the swapfile by,

```bash
sudo chmod 600 /swapfile
```

6.5 Format the file as swap by,

```bash
sudo mkswap /swapfile
```

6.6 Activate the swapfile by,

```bash
sudo swapon /swapfile
```

6.7 Open your workspace

```bash
cd ~/openshc_ws
```

6.8 Compile your workspace using single threaded compiling by,

```bash
catkin build -j1
```

6.9 Make sure the catkin workspace is successfully compiled and source the devel/setup.bash file from your workspace.

```bash
source ~/openshc_ws/devel/setup.bash
```

6.10 You have to source the devel/setup.bash file for each terminal session you want to use SHC. You can edit the .bashrc file to get it automatically sourced to each terminal session. Open the .bashrc file by,

```bash
nano ~/.bashrc
```

6.11 Add the following line to the end of the file and save it.

```bash
source ~/openshc_ws/devel/setup.bash
```

6.12 See [Troubleshooting](troubleshooting.md) if you encounter with any problems.

[Next: Configuring WLAN Settings](shc_raspi_configure_wlan.md)
