# 5. Configuring the Wireless Access Point

[![Syropod Banner](https://i.imgur.com/QyMTwG3.jpg "CSIRO Robotics")](https://research.csiro.au/robotics/)

[Previous: Compiling the Catkin Workspace](shc_raspi4_compile_workspace.md)

These instructions will show you how to setup a wireless access point which starts on boot. This will allow you to access the robot easily using SSH.
PLEASE NOTE: Instructions adapted from [raspberrypi.org](https://www.raspberrypi.org/documentation/configuration/wireless/access-point.md)

5.1 If the pi has been powered off since completing previous steps the date will need to be set again. The date used below is an example only.

```bash
sudo date -s "20 JAN 2020 15:30:25"
sudo apt-get update
```

5.2 To create the AP you will need DNSMasq and HostAPD

```bash
sudo apt install dnsmasq hostapd
```

5.3 As configuration has not yet been completed, turn off the two services

```bash
sudo systemctl stop dnsmasq
sudo systemctl stop hostapd
```

5.4 To use dnsmasq your Pi must have a fixed IP address, access your dhcpcd settings as below

```bash
sudo nano /etc/dhcpcd.conf
```

Scroll to the bottom of the file and add the following. The IP address used is only an example, ensure you pick a value with no duplicates on your network

```apacheconf
interface wlan0
    static ip_address=192.168.50.254/24
    nohook wpa_supplicant
```

To finish setting the IP address restart the daemon

```bash
sudo service dhcpcd restart
```

5.5 To configure the DHCP server it's easiest to start a fresh configuration file. To do this rename the old file so its contents are not lost and create a new file as shown

```bash
sudo mv /etc/dnsmasq.conf /etc/dnsmasq.conf.orig
sudo nano /etc/dnsmasq.conf
```

Add the following to the new dnsmasq.conf

```apacheconf
interface=wlan0
dhcp-range=192.168.50.2,192.168.50.20,255.255.255.0,24h
```

Finally reload the service to update the configuration

```bash
sudo systemctl start dnsmasq
sudo systemctl reload dnsmasq
```

5.6 Next you need to configure HostAPD to create the hotspot. First edit the following file

``` bash
sudo nano /etc/hostapd/hostapd.conf
```

Add the following. Ensure you replace NameOfNetwork, ChosenChannel and NetworkPassword with your desired values

```apacheconf
interface=wlan0
driver=nl80211
ssid=NameOfNetwork
hw_mode=g
channel=ChosenChannel
wmm_enabled=0
macaddr_acl=0
auth_algs=1
ignore_broadcast_ssid=0
wpa=2
wpa_passphrase=NetworkPassword
wpa_key_mgmt=WPA-PSK
wpa_pairwise=TKIP
rsn_pairwise=CCMP
```

Tell the system where the configuration file is saved by editing the following

``` bash
sudo nano /etc/default/hostapd
```

In this file find the line beginning #DAEMON_CONF and replace it with

```apacheconf
DAEMON_CONF="/etc/hostapd/hostapd.conf"
```

5.7 Enable HostAPD with the following

```bash
sudo systemctl unmask hostapd
sudo systemctl enable hostapd
sudo systemctl start hostapd
```

5.8 Finally you'll need to add routing and masquerade which involves editing the files outlined below

```bash
sudo nano /etc/sysctl.conf
```

Uncomment the line "net.ipv4.ip_forward=1"

Add a masquerade for outbound ethernet traffic and save the iptables rule

```bash
sudo iptables -t nat -A  POSTROUTING -o eth0 -j MASQUERADE
sudo sh -c "iptables-save > /etc/iptables.ipv4.nat"
```

Lastly edit /etc/rc.local using a sudo nano command and add the following just before the exit 0 command

```apacheconf
iptables-restore < /etc/iptables.ipv4.nat
```

5.9 Reboot the robot and check the hotspot is visible under the SSID you specified.

[Next: OPTIONAL: Setting Up SHC to Run at Launch](shc_raspi4_run_at_launch.md)
