# Pan-Tilt Hat Notes

A Pimoroni Pan-Tilt HAT can be purchased 
[here](https://shop.pimoroni.com/products/pan-tilt-hat).

The Pan-Tilt HAT github repo is [here](https://github.com/pimoroni/pantilt-hat)

The Python API is described [here](http://docs.pimoroni.com/pantilthat/).

## Raspbian Installation

Python 3:
```bash
pi@raspberrypi:~ $ sudo apt-get install python3-pantilthat
```

Python 2:
```bash
pi@raspberrypi:~ $ sudo apt-get install python-pantilthat
```

Enable the I2C bus with `raspi-config`.
Select `Interfacing Options` and then enable `I2C`.

```bash
pi@raspberrypi:~ $ sudo raspi-config
```


