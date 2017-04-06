# ROS Notes

Kinetic OSX install notes are [here](http://wiki.ros.org/kinetic/Installation/OSX/Homebrew/Source).

If you encounter a `ImportError: No module named _markerlib` error, fix it with:
```bash
$ easy_install distribute
$ pip install --upgrade distribute
```

Kinetic Raspi install notes are [here](http://wiki.ros.org/ROSberryPi/Installing%20ROS%20Kinetic%20on%20the%20Raspberry%20Pi).