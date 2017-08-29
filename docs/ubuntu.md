# Ubuntu Notes

## Installing on a Mac

Good video: https://www.youtube.com/watch?v=IQIaDO9nR6Y

To enable wifi on a Mac: http://sourcedigit.com/19519-how-to-enable-wifi-in-ubuntu-16-04/

## Installing on a Raspi

Download Ubuntu MATE 16.04.2 LTS for Raspberry Pi 2 and 3 systems from [here](https://ubuntu-mate.org/download/)

Open the downloaded file with [Keka](http://www.kekaosx.com/en/)

Run `sudo raspi-config` to expand the filesystem.

## Enable wifi on Raspi

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

## Set Up

Ubuntu requires you to initially login with a keyboard and monitor to setup the
system.

Once logged in, you can:
1) assign the machine a name via the login prompt
2) enable SSH via `raspi-config`
3) expand the filesystem via `raspi-config`
4) turn off GUI on init via `raspi-config`


## Networking

To determine the IP address of the Ubunutu instance, use:

```bash
$ ifconfig -a | grep addr
```

Using ssh to connect to Ubuntu is much better than using the Ubuntu console
because OSX Terminal supports copy and paste.

Enable SSH with: http://ubuntuhandbook.org/index.php/2016/04/enable-ssh-ubuntu-16-04-lts/
