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
$ export ROS_MASTER_URI=http://roscore_machine_name:11311/
```


## ROS Commands

### ROS Nodes
``` 
rosnode list
rosnode info
rosrun [package_name] [node_name]
rosnode ping [node_name]
```

### ROS Topics
``` 
rostopic bw     display bandwidth used by topic
rostopic echo   print messages to screen
rostopic hz     display publishing rate of topic    
rostopic list   print information about active topics
rostopic pub    publish data to topic
rostopic type   print topic type
rosrun rqt_graph rqt_graph
rosrun rqt_plot rqt_plot
```

### ROS Services
```
rosservice list         print information about active services
rosservice call         call the service with the provided args
rosservice type         print service type
rosservice find         find services by service type
rosservice uri          print service ROSRPC uri
```

### ROS Parameters
```
rosparam list           list parameter names
rosparam set            set parameter
rosparam get            get parameter
rosparam load           load parameters from file
rosparam dump           dump parameters to file
rosparam delete         delete parameter
```

## Athenian ROS Configuration

* *roscore* is running on **ros-master**.



