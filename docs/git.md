# Git Notes

A good [Git](https://git-scm.com) tutorial is 
[here](https://try.github.io/levels/1/challenges/1)

## Installation

### OSX 

Install git on OSX with:
```bash
$ brew install git
```

### ev3dev and Raspi
````bash
$ sudo apt-get install git
````

## GitHub Desktop

Download and install [GitHub Desktop](https://desktop.github.com).

## Cloning a Repo

Clone a repo from [Athenian Robotics](https://github.com/athenian-robotics) with:
```bash
$ git clone https://github.com/athenian-robotics/ev3dev-python-intro.git
```

To find the URL for a particular repo, go to it's github page and 
click on the `Clone or download` button and copy the URL in the pop-up
window. If your firewall blocks port 22, make sure that the repo URL begins 
with `https://` and not `git@`. 
You can toggle between the two versions by clicking on `Use HTTPS` and `Use SSH`.

## Setting up a host repo

If a Raspi does not have access to github.com (like on an FRC robot), then 
creating a host repo will make it much easier to update code on the Raspi.

* Create a bare repo and a regular repo on the Raspi for *myproject*:
```bash
$ mkdir git
$ cd git
$ mkdir myproject.git
$ git init --bare myproject.git
$ mkdir myproject
```

* Add a *post-receive* git hook that will trigger a `git pull`   
into */home/pi/git/myproject* whenever a `git push` is done to */home/pi/git/myproject.git*
from a remote machine.

Edit */home/pi/git/myproject.git/hooks/post-receive* and add:
```bash
#!/bin/sh
git --work-tree=/home/pi/git/myproject --git-dir=/home/pi/git/myproject.git checkout -f
echo "*** Updated myproject ***" >&2
```

The `echo` output will be sent back the user as part of the `git push` CLI response.

* Make the hook executable with:
```bash
$ chmod +x /home/pi/git/myproject.git/hooks/post-receive
```

* On the remote machine, clone *myproject* from github and add *myproject.git* as a remote repo with:
```bash
$ git remote add raspi pi@raspberrypi.local:/home/pi/git/myproject.git
```

* You can now push updates from your remote machine to the Raspi with:
```bash
$ git push raspi master
```

In the case of FRC, you would push to *origin* when connected to a network reaching github.com
and you would push to *raspi* when connected to your FRC robot network. 


