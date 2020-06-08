# 7. Configuring WLAN Settings

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Back: Compiling the Catkin Workspace](shc_raspi_compile_workspace.md)

You can configure the WLAN settings in your Raspberry Pi to make it connect to a known Wi-Fi network at startup as follows.

7.1 Enable the wireless interface by,

```bash
sudo ifconfig wlan0
```

* Here wlan0 is the default wireless interface and it might have to be replaced by the name of the wireless interface in your Raspberry Pi.

7.2 Then connect the Raspberry Pi into a known Wi-Fi network by,

```bash
sudo iwconfig wlan0 essid <name> key <password>
```

* Here `<name>` should be replaced by the name of the Wi-Fi network and `<password>` should be replaced by the password of that network. (e.g. sudo iwconfig wlan0 essid home key abcd1234)

7.3 Obtain a dynamic IP address by,

```bash
sudo dhclient wlan0
```

* The above steps indicate how to connect to a wireless network using terminal commands. However to make the Raspberry Pi to connect to a known Wi-Fi network at startup you have to modify the configuration file as follows.

7.4 Open the network configuration file by,

```bash
sudo nano /etc/netplan/50-cloud-init.yaml
```

7.5 Modify the contents of the file as follows to add the WLAN configuration settings in addition to the ethernet configuration settings. (Don't change the ethernet configuration settings)

```yaml
network:
  version: 2
  ethernets:
    eth0:
      dhcp4: true
      match:
        macaddress: b8:27:eb:03:91:12
      set-name: eth0

  wifis:
    wlan0:
      optional: true
      dhcp4: true
      access-points:
        home:
          password: abcd1234
```

* Here `home` and `abcd1234` should be changed with the name and the password of your Wi-Fi network respectively.

7.6 Save the file and check for any syntax errors by,

```bash
sudo netplan --debug generate
```

* Indentation in YAML files is critical and give proper spacing if suggested.

7.7 Reboot the Raspberry Pi and check whether it connects automatically to your Wi-Fi network.

```bash
sudo reboot
```

[Next: Enabling SSH](shc_raspi_enable_ssh.md)
