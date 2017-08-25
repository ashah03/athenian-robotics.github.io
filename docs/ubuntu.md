# Ubuntu Notes

## Set Up

Ubuntu requires you to initially login with a keyboard and monitor to setup the
system.

Once logged in, you can:
1) assign the machine a name via the login prompt
2) enable SSH via `raspi-config`
3) expand the filesystem via `raspi-config`
4) turn off GUI on init via `raspi-config`

## Enable wifi

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


## Networking

To determine the IP address of the Ubunutu instance, use:

```bash
$ ifconfig -a | grep addr
```

Using ssh to connect to Ubuntu is much better than using the Ubuntu console
because OSX Terminal supports copy and paste.

Download Ubuntu MATE 16.04.2 LTS for Raspberry Pi 2 and 3 systems from [here](https://ubuntu-mate.org/download/)

Open the downloaded file with [Keka](http://www.kekaosx.com/en/)

Run `sudo raspi-config` to expand the filesystem.


## Installing on a Mac

Good video: https://www.youtube.com/watch?v=IQIaDO9nR6Y
