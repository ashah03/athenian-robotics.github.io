# XQuartz Notes

`XQuartz` is an X server for OSX.

## Installation
Download and install XQuartz from [here](https://www.xquartz.org).

Type this on the Mac:
```bash
$ xhost + 
```
Add this line to ~/.profile or type it in the shell on the Raspi:
```
export DISPLAY=pleiku.local:0.0 
```
    
Verify the setup on the Raspi with:
```bash
$ lxsession
```

Note: If you are using VirtualBox, you will want to use the IP address
of your mac, since its hostname may not be visible to the virtual instance.


