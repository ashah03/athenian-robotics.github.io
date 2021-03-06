# Unicorn Hat Notes

A Unicorn HAT can be purchased 
[here](https://shop.pimoroni.com/products/unicorn-hat)

The Unicorn HAT github repo is [here](https://github.com/pimoroni/unicorn-hat).

Examples are [here](https://github.com/pimoroni/unicorn-hat/tree/master/examples).

## Raspbian Installation

Python 2
```bash
$ sudo apt-get install python-pip python-dev
$ sudo pip install unicornhat
```

Python 3
```bash
$ sudo apt-get install python3-pip python3-dev
$ sudo pip3 install unicornhat
```

If you get an error message *Can't open /dev/mem: Permission denied*, then run the program with `sudo`.

If you get random LEDs blinking, make sure the sound is routed to HDMI by
adding these two lines to /boot/config.txt and rebooting:

```
hdmi_force_hotplug=1
hdmi_drive=2
```



<iframe src="https://player.vimeo.com/video/105482682" width="640" height="360" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>

