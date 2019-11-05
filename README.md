# RTAB-Map in ROS with Kinect Xbox-360

## Requirements
* Ubuntu 16.04. 

* ROS Kinetic ([Installation](https://github.com/ghunshoot/SLAM/blob/master/Installing_ROS.md)).
* Libfreenect or OpenNI

## Installing
### Installing Libfreenect (ONLY IN UBUNTU 16.04)
```
  $ sudo apt-get install ros-kinetic-freenect-launch
```
Test your kinect.
```
$ freenect-glview
```
### Installing Openni (ONLY IN UBUNTU 18.04, NOT TESTED IN UBUNTU 16.04)
```
  $ sudo apt-get install ros-melodic-openni-launch
```
### Installing rtabmap-ros
#### For kinetic.
```
  $ sudo apt-get install ros-kinetic-rtabmap-ros
```
#### For melodic.
```
  $ sudo apt-get install ros-melodic-rtabmap-ros
```
## Testing
In two different terminals.

For Freenect
```
$ roslaunch freenect_launch freenect.launch depth_registration:=true
```
For OpenNI
```
roslaunch openni_launch openni.launch depth_registration:=true
```
```
$ roslaunch rtabmap_ros rtabmap.launch rtabmap_args:="--delete_db_on_start"
```
A window like this will open.
![alt text](https://github.com/ghunshoot/RTAB-Map-ROS-Kinect/blob/master/Img/4.png)
