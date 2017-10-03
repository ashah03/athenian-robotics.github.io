# Misc Python Packages

## pyFirmata

Detailed instructions for [pyFirmata](https://github.com/tino/pyFirmata) are 
[here](http://pyfirmata.readthedocs.io/en/latest/).

Install *pyFirmata* with:
```bash
$ pip install pyfirmata
```

## numpy

A detailed description of the *numpy* Python package is [here](http://www.numpy.org).

Install *numpy* with:
```bash
$ pip install numpy
```

## pyserial 

A detailed description of the *pyserial* Python package is [here](https://pythonhosted.org/pyserial/).

Install *pyserial* with:
```bash
$ pip install pyserial
```

## imutils 

A detailed description of the *imutils* Python package is [here](https://github.com/jrosebr1/imutils).

Install *imutils* with:
```bash
$ pip install imutils
```

## Tkinter
A good [Tkinter](https://wiki.python.org/moin/TkInter) introduction 
is [here](http://effbot.org/tkinterbook/tkinter-index.htm).

## MQTT Client 

### OSX Installation

Python 2
```bash
$ pip install paho-mqtt
```

Python 3
```bash
$ pip3 install paho-mqtt
```

### Raspbian Installation

Python 2
```bash
$ sudo pip install paho-mqtt
```

Python 3
```bash
$ sudo pip3 install paho-mqtt
```


### MQTT Client Programming Notes

Usage of wildcards in topic filters is described 
[here](http://www.hivemq.com/blog/mqtt-essentials-part-5-mqtt-topics-best-practices).


## gR# Misc Python Packages

## pyFirmata

Detailed instructions for [pyFirmata](https://github.com/tino/pyFirmata) are 
[here](http://pyfirmata.readthedocs.io/en/latest/).

Install *pyFirmata* with:
```bash
$ pip install pyfirmata
```

## Tkinter
A good [Tkinter](https://wiki.python.org/moin/TkInter) introduction 
is [here](http://effbot.org/tkinterbook/tkinter-index.htm).

## MQTT Client 

### OSX Installation

Python 2
```bash
$ pip install paho-mqtt
```

Python 3
```bash
$ pip3 install paho-mqtt
```

### Raspbian Installation

Python 2
```bash
$ sudo pip install paho-mqtt
```

Python 3
```bash
$ sudo pip3 install paho-mqtt
```


### MQTT Client Programming Notes

Usage of wildcards in topic filters is described 
[here](http://www.hivemq.com/blog/mqtt-essentials-part-5-mqtt-topics-best-practices).


## gRPC 

### gRPC Presentations

[Enabling Googley Microservices with http2 and gRPC](https://www.slideshare.net/borisovalex/enabling-googley-microservices-with-http2-and-grpc)

### gRPC Installation for Python

Detailed installation instructions are [here](http://www.grpc.io/docs/quickstart/python.html).

Install [gRPC](http://www.grpc.io/docs/guides/) with:

OSX:
```bash
$ pip install grpcio
$ pip install grpcio-tools 
```

Raspbian:
```bash
$ sudo apt-get install python-dev
$ sudo pip install grpcio
$ sudo pip install grpcio-tools 
```

If the installation fails with `ImportError: No module named Cython`, install *Cython* with:
```bash
$ pip install Cython
```

## OpenCV 

OpenCV is described in detail [here](http://opencv.org).

A great OpenCV resource is [pyimagesearch](http://www.pyimagesearch.com).

A good OpenCV Python tutorial is 
[here](http://docs.opencv.org/3.0-beta/doc/py_tutorials/py_tutorials.html).

### OSX

Install OpenCV 3 with:

```bash
$ brew tap homebrew/science
$ brew install opencv3 --with-contrib --with-python3 --with-java --with-examples 
$ echo /usr/local/opt/opencv3/lib/python2.7/site-packages >> /usr/local/lib/python2.7/site-packages/opencv3.pth
```

Detailed instructions are 
[here](http://www.pyimagesearch.com/2016/12/19/install-opencv-3-on-macos-with-homebrew-the-easy-way/).

<aside class="warning">
Warning: As of OpenCV 3.2.0, the --with-python3 option does not seem to work. Until this is 
addressed, use Python 2.7 with OpenCV 3.
</aside>

### Ubuntu

Instructions for installing OpenCV 3 on Ubuntu are [here](http://www.learnopencv.com/install-opencv3-on-ubuntu/).
### Raspbian

Detailed instructions are 
[here](http://www.pyimagesearch.com/2016/04/18/install-guide-raspberry-pi-3-raspbian-jessie-opencv-3/).
Make sure to use version `3.2.0` instead of `3.1.0`.

### Windows

Detailed instructions are [here](http://www.learnopencv.com/install-opencv3-on-windows/)

### Displaying Raspi OpenCV camera images to a Mac

1) Set **DISPLAY** to use the OSX machine (in this case *my-mac.local*). 
On the Raspi type:
```bash
$ export DISPLAY=my-mac.local:0
```

2) Start the *[X](https://en.wikipedia.org/wiki/X_Window_System) server* 
[XQuartz](https://www.xquartz.org) on the OSX machine.

3) Add the Raspi host name to enable connections to the X server (in this case *my-raspi*). 
On the OSX machine type:
```bash
$ xhost + my-raspi
my-raspi being added to access control list
```

