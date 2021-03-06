# OpenCV 

* [OpenCV Home](http://opencv.org)
* [pyimagesearch](http://www.pyimagesearch.com)
* [OpenCV Python tutorial](http://docs.opencv.org/3.0-beta/doc/py_tutorials/py_tutorials.html)
* [Setting up OpenCV on Raspian Stretch](http://www.pyimagesearch.com/2017/09/04/raspbian-stretch-install-opencv-3-python-on-your-raspberry-pi/)

## Setup

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

