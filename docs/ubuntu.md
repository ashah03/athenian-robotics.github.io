# Ubuntu Notes

General Linux admin notes [here](./linux.md).

## Installing on Mac boot disk

Good video: https://www.youtube.com/watch?v=IQIaDO9nR6Y

[This](http://sourcedigit.com/19519-how-to-enable-wifi-in-ubuntu-16-04/) describes how to enable wifi on a Mac.

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

