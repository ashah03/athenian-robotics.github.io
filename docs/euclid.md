# Intel Euclid Notes

Tutorials are [here](http://www.euclidcommunity.intel.com)

Source code is [here](https://github.com/inteleuclid)

Euclid workspace is at: /intel/euclid/euclid_ws

## Connecting

Connect to the euclid app at http://euclid.local

`ssh` into the Euclid with: `ssh euclid@euclid` (PW: euclid)

## Changing ROS vars

The env var **ROS_MASTER_URI** is set in */intel/euclid/config/settings.ini*

After editing the *settings.ini* file, reset services with: 
```
sudo service oobe-init restart-oobe
```

To stop services:
```
sudo service oobe-init 
```

To start services:
```
sudo service oobe-init start
```

## Config

`roscore` is started on init at: `/intel/euclid/oobe-services/ros_services/S1ROS/init.sh`

Logs are in: `/home/euclid/.ros/log/`

## Forum

Intel answers questions at: https://communities.intel.com/community/tech/realsense/overview