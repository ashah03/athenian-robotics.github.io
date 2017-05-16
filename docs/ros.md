# ROS Notes

Kinetic OSX install notes are [here](http://wiki.ros.org/kinetic/Installation/OSX/Homebrew/Source).

If you encounter a `ImportError: No module named _markerlib` error, fix it with:
```bash
$ easy_install distribute
$ pip install --upgrade distribute
```

Kinetic Raspi install notes are [here](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Kinetic%20on%20the%20Raspberry%20Pi).

A good tutorial is [here](http://wiki.ros.org/ROS/Tutorials).

A good wiki is [here](http://wiki.ros.org/roscore).


* The default *roscore* port is 11311

* The env var that is used to determine where *roscore* is running is **ROS_MASTER_URI**.

```bash
$ export ROS_MASTER_URI=http://roscore_machine_name:1234/
```