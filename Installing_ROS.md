# Ros Installation
The official documentation and installation is [here](http://wiki.ros.org/kinetic/Installation/Ubuntu), but I presented some issues. Here I will show how I could install correctly ROS Kinetic in Ubuntu 16.04 (10/31/2019).

First we start checkmarking all in System Settings > Software and Updates > Ubuntu Software, Other Software, and Updates.
Also in Ubuntu Software we select `Download from: Main`. Notice when close the window it will start updating the cache. When finish updating it bring back "Failed to download repository information", ignore and go on.
![alt text](https://github.com/ghunshoot/RTAB-Map-ROS-Kinect/blob/master/Img/1.png)

Setup your sources.list.
```
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-  latest.list'
```
Set up your keys.
```
$ sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```
Proceed to install ROS Kinetic.
```
$ sudo apt-get update

$ sudo apt-get install -f

$ sudo apt-get install ros-kinetic-desktop-full

```
Initialize rosdep
```
$ sudo rosdep init
$ rosdep update
```
Environment setup
```
$ echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```
Dependencies for building packages
```
$ sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential
```
