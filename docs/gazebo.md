k# Gazebo Notes

A Gazebo description is [here](http://www.ros.org/news/2017/05/steffi-paepcke-and-louise-poubel-osrf-whats-new-in-gazebo-upgrading-your-simulation-user-experience.html)

## Installation

Install gazebo8 with ([details](http://gazebosim.org/tutorials?tut=install_ubuntu)):

```bash
$ curl -ssL http://get.gazebosim.org | sh
$ sudo apt-get install ros-kinetic-gazebo8-ros
```

Build gazebo from source with:

```bash
sudo apt-get remove '.*gazebo.*' '.*sdformat.*' '.*ignition-math.*' '.*ignition-msgs.*' '.*ignition-transport.*'
hg clone https://bitbucket.org/osrf/gazebo /tmp/gazebo
cd /tmp/gazebo
hg pull && hg update gazebo7
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr/local ../
make -j4
sudo make install
# or
sudo make uninstall
```

Install source for *gazebo_ros_pkgs* into *~/catkin_ws/src* and then:
```bash
sudo apt-get install gazebo7=7.0.0+dfsg-2 libgazebo7=7.0.0+dfsg-2 gazebo7-common=7.0.0+dfsg-2
sudo apt-get install ros-kinetic-gazebo-ros-pkgs
sudo apt-get install ros-kinetic-gazebo-ros-control
```