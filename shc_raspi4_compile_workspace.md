# 4. Compiling the Catkin Workspace

[Previous: Configuring the Catkin Workspace](shc_create_workspace_prebuilt_image.md)

As the Raspberry Pi 4 has options up to 4GB of RAM a swapfile is often no longer needed for onboard compilation. If you have purchased the 1GB option, please follow compilation instructions for the Raspberry Pi 3 found [here](shc_raspi_compile_workspace.md)

6.1 Open your workspace

```bash
cd ~/openshc_ws
```

6.2 Compile your workspace using a sensible number of threads for your Pi RAM option.

2GB RAM Model

```bash
catkin build -j1
```

4GB RAM Model

```bash
catkin build -j3
```

For this model -j4 for four jobs may also be acceptable, however spikes in RAM usage during compilation make this less reliable. Three jobs compiles in less than 10 minutes and is a good balance between speed and reliability.

6.3 Source your workspace

```bash
source devel/setup.bash
```

6.4 To ensure the workspace stays sourced, open your .bashrc file

```bash
sudo nano ~/.bashrc
```

and add the following line to the end and save it.

```bash
source ~/openshc_ws/devel/setup.bash
```

6.5 See [Troubleshooting](troubleshooting.md) if you encounter any problems.

[Next: Configuring The Wireless Access Point](shc_raspi4_configure_AP.md)
