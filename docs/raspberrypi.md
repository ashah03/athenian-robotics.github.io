# Raspberry Pi Notes

## Install Raspian 

### OSX

* Download the [Raspbian distro](https://www.raspberrypi.org/downloads/raspbian/).

*  Burn the .img file to a SD card with [Etcher](https://etcher.io).

*  **Important:** Remove and reinsert SD card and add a file named `ssh` to the SD card boot partition.
This will enable `ssh` on the Raspi.
```bash
$ touch /Volumes/boot/ssh
```

*  Eject the SD card from the Mac, connect an ethernet cable to the Raspi, and power up the Raspi.

*  Login to the Raspi with `ssh` using the username *pi* and password *raspberry*.
```bash
$ ssh pi@raspberrypi
Are you sure you want to continue connecting (yes/no)? yes
Password: raspberry
pi@raspberrypi:~ 
```

If you get a *Host key verification failed* error when using `ssh`, 
remove the *raspberry.local* entry from ~/.ssh/known_hosts on your Mac with:

```bash
$ nano ~/.ssh/known_hosts
```

## Resize root partition

Resize the root partition with `raspi-config`.
Choose "Expand Filesystem", tab to <Finish> and then reboot.

```bash
pi@raspberrypi:~ $ sudo raspi-config
```

## Update distro
Update the Raspbian distro to the latest and greatest bits with:
```bash
pi@raspberrypi:~ $ sudo apt-get update
pi@raspberrypi:~ $ sudo apt-get upgrade
pi@raspberrypi:~ $ sudo apt-get dist-upgrade
pi@raspberrypi:~ $ sudo reboot now
```

## Change hostname
Multiple Raspis on your network cannot share the same hostname. Change your hostname with:

```bash
pi@raspberrypi:~ $ sudo nano /etc/hostname
pi@raspberrypi:~ $ sudo reboot now
```

## Enable Wi-Fi
```bash
pi@raspberrypi:~ $ sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

Add a network entry for each SID with which the Raspi will need to connect:
```snakeyaml
network={
    ssid="MyWiFiNetwork1"
    psk="the_password1"
    key_mgmt=WPA-PSK
}

network={
    ssid="MyWiFiNetwork2"
    psk="the_password2"
    key_mgmt=WPA-PSK
}
```

## Enable VNC

Enable VNC with `raspi-config`. Choose the `Interfacing Options` and then 
the `VNC` option. Tab to <Finish> and then reboot.

Start the VNC server with:
```bash
pi@raspberrypi:~ $ vncserver :1 -geometry 1024x728 -depth 24
```

Use `-geometry 2048x1456` for a larger display.

Download a *VNCViewer* app from 
[here](https://www.realvnc.com/download/viewer/). 

Start the *VNCViewer* app on the Mac and connect to the Raspi at `raspberrypi:1`.

## Enable a camera
Enable a Pi camera with `raspi-config`. Select the `Interfacing Options` and then the `Camera` option.
Tab to <Finish> and then reboot.
```bash
pi@raspberrypi:~ $ sudo raspi-config
```

## Install File sharing

Details are [here](http://www.instructables.com/id/How-to-share-files-between-Mac-OSX-and-Raspberry-P/?ALLSTEPS).

Enable file sharing with:
```bash
pi@raspberrypi:~ $ sudo apt-get install netatalk
```

