# 8. Enabling SSH

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Back: Configuring WLAN Settings](shc_raspi_configure_wlan.md)

SSH can be used to remotely login into your Raspberry Pi using a wireless network. This allows you to easily access the Raspberry Pi after the robot has been assembled without having to connect any interfacing hardware. By default SSH is installed with Ubuntu Server 18.04.

8.1 Check the status of SSH by,

```bash
sudo systemctl status ssh.service
```

8.2 If SSH is enabled connect the Raspberry Pi to a known Wi-Fi network like a wireless router or a mobile hotspot. [Configuring WLAN Settings](shc_raspi_configure_wlan.md)

8.3 Connect your PC or the laptop to the same Wi-Fi network.

8.4 SSH into the Raspberry Pi from your PC or laptop by,

```bash
ssh username@ip-address
```

* Here username should be the username of the Raspberry Pi (default is ubuntu) and ip-address should be the ip address of the Raspberry Pi obtained by the router or the mobile hotspot. You can find the ip-address of the Raspberry Pi by logging into the router or the mobile hotspot. (e.g. ssh ubuntu@192.168.1.1)

8.5 Enter your log in details and log in to the Raspberry Pi.

[Next: Preparing the Legged Robot](shc_raspi_prepare_hexapod.md)
