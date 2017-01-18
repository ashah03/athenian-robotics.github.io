# Python Administration

## Installation

### OSX

Installation details are 
[here](http://docs.python-guide.org/en/latest/starting/install3/osx/).

Python3 requires `gcc`, which you can get by installing 
[XCode](http://developer.apple.com/xcode/) or 
[Command Line Tools](https://developer.apple.com/downloads/).

Install python3 and pip3 with:
```bash
$ brew install python3
```

### EV3

Install python3 and pip3:
```bash
$ sudo apt-get install python3
$ sudo apt-get install python3-pip
```


## Package Management

Determine installed packages with:
```bash
$ pip list 
```

Determine outdated packages with:
```bash
$ pip list --outdated
```

Install a package with:
```bash
$ pip install pkg_name
```

Update a package with:
```bash
$ pip install --upgrade pkg_name
```

