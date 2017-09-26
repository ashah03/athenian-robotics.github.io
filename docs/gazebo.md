# Gazebo Notes

A Gazebo description is [here](http://www.ros.org/news/2017/05/steffi-paepcke-and-louise-poubel-osrf-whats-new-in-gazebo-upgrading-your-simulation-user-experience.html)

## Installation

Install gazebo8 with ([details](http://gazebosim.org/tutorials?tut=install_ubuntu)):

```bash
$ curl -ssL http://get.gazebosim.org | sh
$ sudo apt-get install ros-kinetic-gazebo8-ros
```

Building from source details:

```bash
hg clone https://bitbucket.org/osrf/gazebo /tmp/gazebo
cd /tmp/gazebo
hg pull && hg update gazebo8
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr/local ../
make -j4
sudo make install
# or
sudo make uninstall
```