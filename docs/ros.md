# ROS Notes

Kinetic OSX install notes are [here](http://wiki.ros.org/kinetic/Installation/OSX/Homebrew/Source) (Do not use).

If you encounter a `ImportError: No module named _markerlib` error, fix it with:
```bash
$ easy_install distribute
$ pip install --upgrade distribute
```

Ubuntu Kinetic Raspi install notes are [here](http://wiki.ros.org/kinetic/Installation/Ubuntu).

A good tutorial is [here](http://wiki.ros.org/ROS/Tutorials).

* The env var that is used to determine where *roscore* is running is **ROS_MASTER_URI**.

```bash
$ export ROS_MASTER_URI=http://roscore_machine_name:11311/
```

## ROS on Docker
Run *roscore* with:
```bash
$ docker run -it --rm  -p11311:11311  ros roscore
```

## ROS on Raspbian

Instructions for installing Kinetic on Raspbian are [here](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Kinetic%20on%20the%20Raspberry%20Pi)

## ROS Commands

### ROS Utilities
``` 
roslaunch [package] [filename.launch]
rqt
rqt_graph
rqt_console
rqt_logger_level
rqt_plot
```

### ROS Nodes
``` 
rosnode list
rosnode info
rosrun [package_name] [node_name]
rosnode ping [node_name]
```

### ROS Topics
``` 
rostopic list              print information about active topics
rostopic hz topic_name     display publishing rate of topic    
rostopic bw topic_name     display bandwidth used by topic
rostopic pub topic_name    publish data to topic
rostopic echo topic_name   print messages to screen
rostopic type topic_name   print topic type
```

### ROS Services
```
rosservice list                print information about active services
rosservice call service_name   call the service with the provided args
rosservice type service_name   print service type
rosservice find service_name   find services by service type
rosservice uri service_name    print service ROSRPC uri
```

### ROS Parameters
```
rosparam list                  list parameter names
rosparam set param_name value  set parameter
rosparam get param_name        get parameter
rosparam load file_name        load parameters from file
rosparam dump file_name        dump parameters to file
rosparam delete param_name     delete parameter
```

### ROS *msg* and *srv* Files
``` 
rosmsg show     Show message description
rosmsg list     List all messages
rosmsg md5      Display message md5sum
rosmsg package  List messages in a package
rosmsg packages List packages that contain messages

rossrv show [service type]
```

### ROS Filesystem
``` 
roscd [locationname[/subdir]]
rosls [locationname[/subdir]]
rospack find [package_name]
```


### Examples

When running `rosrun rospy_tutorials talker` and
`rosrun rospy_tutorials listener`, monitor the messages with:
`rostopic echo chatter`.


A Gazebo description is [here](http://www.ros.org/news/2017/05/steffi-paepcke-and-louise-poubel-osrf-whats-new-in-gazebo-upgrading-your-simulation-user-experience.html)




