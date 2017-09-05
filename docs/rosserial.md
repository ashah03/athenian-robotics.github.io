# Arduino rosserial Notes

Details are [here](http://wiki.ros.org/rosserial_arduino/Tutorials)

## Installation

1) In the Arduino IDE menu choose Sketch-->Include Library-->Manage Libraries, search 
for **rosserial** and install the library.

2) Install the binaries with:
```bash
$ sudo apt-get install ros-kinetic-rosserial-arduino
$ sudo apt-get install ros-kinetic-rosserial
```

## Demos

### Hello World

In the Arduino IDE menu, load the **Hello World** sketch from File-->Examples-->RosserialArduinoLibrary.

Make sure *roscore* is running and **ROS_MASTER_URI** is set properly.

Run the client application with: 
```bash
$ rosrun rosserial_python serial_node.py /dev/ttyASM0
```

Check the values with:
```bash
$ rostopic echo chatter
```