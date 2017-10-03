# ROS Admin 

A good tutorial is [here](http://wiki.ros.org/ROS/Tutorials).

Some ROS demos are [here](https://github.com/athenian-robotics/ros-demos).

## ROS environment variables

The *~/.bashrc* file should contain:

```bash
source /opt/ros/kinetic/setup.bash
source ~/catkin_ws/devel/setup.bash

export TURTLEBOT3_MODEL=burger
export ROS_HOSTNAME=machine1.local
export ROS_MASTER_URI=http://machine2:11311
```

## ROS on Ubuntu

Installation instructions are [here](http://wiki.ros.org/kinetic/Installation/Ubuntu)

If you want gazebo8, do not install the *ros-kinetic-desktop-full* package because it includes gazebo7.
Use the *ros-kinetic-desktop* package instead and install gazebo8 seperately.

Install *ros-kinetic-desktop* in order to get rospy_tutorials.

## ROS on Raspi

Use Ubuntu MATE, not Raspbian.

Download Ubuntu MATE 16.04.2 from [here](https://ubuntu-mate.org/download/)

## ROS on Jetson TX2

If `sudo rosdep init` returns an error about a website being down, fix it with:
```bash
$ sudo c_rehash /etc/ss/certs
```
 
## ROS on Docker
Run *roscore* with:
```bash
$ docker run -it --rm  -p11311:11311  ros roscore
```

### ROS uninstall

As described [here](https://answers.ros.org/question/57213/how-i-completely-remove-all-ros-from-my-system/):

```bash
$ sudo apt-get remove ros-*
```

### Video Server

Details of the *web_video_server* package are [here](web_video_server).

Install *web_video_server* the with:
```bash
$ sudo apt-get install ros-kinetic-web-video-server
```

Run *web_video_server* with:
```bash
$ rosrun web_video_server web_video_server
```

## ROS IDE

The RoboWare IDE is [here](http://www.roboware.me/#/)




