# Raspberry Pi Zero W Notes

## Configuring to Emulate Ethernet Over USB

Detailed description is [here](https://www.thepolyglotdeveloper.com/2016/06/connect-raspberry-pi-zero-usb-cable-ssh/)

1) Burn an SD card with Raspbian

2) Mount SD card 

3) Add this to the bottom of  *config.txt* :
```
dtoverlay=dwc2
```

4) Add this to *cmdline.txt* right after *rootwait*:
```
modules-load=dwc2,g_ether
```

5) Enable `ssh` with:
```bash
$ touch /Volumes/boot/ssh
```

6) Eject the SD card, place it in the RaspiPi Zero W and power it with a USB cable from your
computer using the USB port on the Raspi.

7) Login to the Raspi with:
```bash
$ ssh pi@raspberrypi.local  (password raspberry)
```

## Enable WiFi

Detailed description is [here](https://www.thepolyglotdeveloper.com/2016/02/use-your-raspberry-pi-as-a-headless-system-without-a-monitor/)

1) Scan for available networks with:
```bash
$ sudo iwlist wlan0 scan
```

2) Add the desired SID to */etc/wpa_supplicant/wpa_supplicant.conf*:
```
network={
    ssid="your_network_ssid_here"
    psk="your_wifi_password"
}
```

3) Reboot the Raspi with:
```bash
$ sudo reboot
```