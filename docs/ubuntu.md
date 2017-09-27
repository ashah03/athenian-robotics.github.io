# Ubuntu Notes

## Installing on Mac boot disk

Good video: https://www.youtube.com/watch?v=IQIaDO9nR6Y

To enable wifi on a Mac: http://sourcedigit.com/19519-how-to-enable-wifi-in-ubuntu-16-04/

## Installing Desktop on Virtual Box

After installing Desktop, click on **Additional Drivers** in **Software & Updates**
and add machine-specific drivers.

Under the VirtualBox Networking options, set "Attached to:" to "Bridged Adapter"

To get hostname to reference network address rather than localhost, remove
host name from `/etc/hosts/`

After downloading the Ubuntu distro, convert it from a *.img.xz* file to a *.img* file with:
```bash
$ brew install xz
$ xz -d file-to-extract.xz
```

## Raspi Notes

Download Ubuntu MATE 16.04.2 LTS for Raspberry Pi 2 and 3 systems from [here](https://ubuntu-mate.org/download/)

Open the downloaded file with [Keka](http://www.kekaosx.com/en/)

Run `sudo raspi-config` to expand the filesystem.

Ubuntu desktop requires you to initially login with a keyboard and monitor to setup the
system.

Once logged in, you can:
1) assign the machine a name via the login prompt
2) enable SSH via `raspi-config`
3) expand the filesystem via `raspi-config`
4) turn off GUI on init via `raspi-config`

1) Add this to */etc/network/interfaces* :
```
allow-hotplug wlan0
iface wlan0 inet dhcp
wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```

2) Scan for available networks with:
```bash
$ sudo iwlist wlan0 scan
```

3) Add the desired SID to */etc/wpa_supplicant/wpa_supplicant.conf* :
```
network={
    ssid="your_network_ssid_here"
    psk="your_wifi_password"
}
```

Install Chromium with:
```bash
$ sudo apt-get install chromium-browser
```

## Ubuntu Mate Wifi Fixes

If the wifi choices are stippled, try this:
* Run: *sudo /etc/init.d/networking restart*
* Edit file **/etc/NetworkManager/NetworkManager.conf**
* Change managed=false to managed=true
* Run: *sudo killall NetworkManager*

To manage wifi connection via a config file, add this to **/etc/network/interfaces**:
```
allow-hotplu wlan0
iface wlan0 inet dhcp
wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```
If a device is not managed in **/etc/network/interfaces**, then it will be avialable via the GUI.


## General installation

Enable SSH with: 

```bash
$ sudo apt-get install openssh-server
```

Install MDNS (enabling hostname.local usage) with: 

```bash
$ sudo apt-get install avahi-daemon
```

