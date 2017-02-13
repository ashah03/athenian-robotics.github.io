# Raspberry Pi Notes

## Install Raspian 

### OSX

* Download the [Raspbian distro](https://www.raspberrypi.org/downloads/raspbian/raspbian.md).

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
remove the *raspberry.local* entry from ~/.ssh/known_hosts on the Mac with:

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
Detailed instructions are 
[here](http://www.makeuseof.com/tag/setup-wi-fi-bluetooth-raspberry-pi-3/)

Discover what SIDs are available with:
```bash
pi@raspberrypi:~ $ iwlist wlan0 scan
```

Add a *network* entry to */etc/wpa_supplicant/wpa_supplicant.conf*
for each SID with which the Raspi will need to connect:
```bash
pi@raspberrypi:~ $ sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

The *network* entries should look like:
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

Restart the Raspi WiFi with:
```bash
pi@raspberrypi:~ $ sudo ifdown wlan0
pi@raspberrypi:~ $ sudo ifup wlan0
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

## Install Python

Install Python 2 with:
```bash
pi@raspberrypi:~ $ sudo apt-get install python python-pip python-dev
```

Install Python 3 with:
```bash
pi@raspberrypi:~ $ sudo apt-get install python3 python3-pip python3-dev
```

## Set up ssh to not ask for a password

Run `ssh-keygen` on the Mac, and hit return when asked for file in which to save the key and the passphrase.
This will generate a public and private keys stored in *~/.ssh/id_rsa* and *~/.ssh/id_rsa.pub*.

```bash
$ ssh-keygen
```

Add the contents of *~/.ssh/id_rsa.pub* on the Mac (using copy and paste) 
into *~/.ssh/authorized_keys* on the Raspi.

```bash
$ sudo nano ~/.ssh/authorized_keys
```
Set the proper permissions for *~/.ssh/authorized_keys* with:
```bash
$ chmod 600 ~/.ssh/authorized_keys
```

You should now be able to ssh to the Raspi without a password.

## Simplify ssh logins

To log into a Raspi with `ssh raspi` instead of `ssh pi@raspi.local`, add this to your *~/.ssh/config* file:
```bash
Host raspi, raspi.local
  HostName raspi.local
  User pi
  StrictHostKeyChecking no
  UserKnownHostsFile /dev/null
```

Ensure that *~/.ssh/config* is visible only to you by setting the permissions with:
```bash
$ sudo chmod 400 ~/.ssh/config
```

The *StrictHostKeyChecking no* option will prevent authenticity prompts from appearing during ssh logins 
and when doing git pushes with `git push raspi master`. 
You will no longer see prompts like this:
```
The authenticity of host 'raspi.local (fe84::d84b:3c2:9ba9:afa7%en0)' can't be established.
ECDSA key fingerprint is SHA256:g+fFiMPfdWH8Lwi6eKjAOWgYoTfDAPh00GnsLLE88fk.
Are you sure you want to continue connecting (yes/no)? 
```

The *UserKnownHostsFile /dev/null* option will prevent ssh from writing to *.ssh/known_hosts*
and then later failing when host keys change. In general, this is not a good security practice,
but it is acceptable when working with local Raspis since you are on a private LAN and
not likely dealing with malicious hosts.

## Install File sharing

Details are [here](http://www.instructables.com/id/How-to-share-files-between-Mac-OSX-and-Raspberry-P/?ALLSTEPS).

Enable file sharing with:
```bash
pi@raspberrypi:~ $ sudo apt-get install netatalk
```

## Misc Raspbian Links

[Useful Raspi Commands](http://www.circuitbasics.com/useful-raspberry-pi-commands/)



