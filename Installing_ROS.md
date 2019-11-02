# Ros Installation
The official documentation and installation is [here](http://wiki.ros.org/kinetic/Installation/Ubuntu), but I presented some issues. Here I will show how I could install correctly ROS Kinetic in Ubuntu 16.04 (10/31/2019).

First we start checkmarking all in System Settings > Software and Updates > Ubuntu Software, Other Software, and Updates.
Also in Ubuntu Software we select `Download from: Main`. Notice when close the window it will start updating the cache. When finish updating it bring back "Failed to download repository information", ignore and go on.

![alt text](https://github.com/ghunshoot/RTAB-Map-ROS-Kinect/blob/master/Img/1.png)

![alt text](https://github.com/ghunshoot/RTAB-Map-ROS-Kinect/blob/master/Img/2.png)

![alt text](https://github.com/ghunshoot/RTAB-Map-ROS-Kinect/blob/master/Img/3.png)

Setup your sources.list.
```
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
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

sudo apt install ros-melodic-desktop-full

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
$ sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential python-catkin-tools python3-dev python3-numpy 
```
Test we have correctly setup the environment
```
$ printenv | grep ROS
```
Setup bash
```
source /opt/ros/kinetic/setup.bash
```
Create a ROS Workspace
```
$ pip install catkin_pkg or pip3 install catkin_pkg (if you're using pip3)
$ mkdir -p ~/catkin_ws/src && cd ~/catkin_ws/

# For working in Python3.7
$ catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3 -DPYTHON_INCLUDE_DIR=/usr/include/python3.7m -DPYTHON_LIBRARY=/usr/lib/libpython3.7m.so

# For working in Python3.6
$ catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3 -DPYTHON_INCLUDE_DIR=/usr/include/python3.6m -DPYTHON_LIBRARY=/usr/lib/libpython3.6m.so

# For working in Python3.5
$ catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3 -DPYTHON_INCLUDE_DIR=/usr/include/python3.5m -DPYTHON_LIBRARY=/usr/lib/libpython3.5m.so

$ source devel/setup.bash

$ echo $ROS_PACKAGE_PATH # return this path /home/youruser/catkin_ws/src:/opt/ros/kinetic/share
```
