# RTAB-Map in ROS with Kinect Xbox-360

## Requirements
* Ubuntu 16.04. 

* ROS Kinetic ([Installation](https://github.com/ghunshoot/SLAM/blob/master/Installing_ROS.md)).
* Libfreenect.

## Installing
### Installing Libfreenect
```
  $ sudo apt-get install ros-kinetic-freenect-launch
```
Test your kinect.
```
$ freenect-glview
```
### Installing rtabmap-ros
```
  $ sudo apt-get install ros-kinetic-rtabmap-ros
```
## Testing
In two different terminals. 
```
$ roslaunch freenect_launch freenect.launch depth_registration:=true\
```
```
$ roslaunch rtabmap_ros rtabmap.launch rtabmap_args:="--delete_db_on_start"
```
A window like this will open.
![alt text](https://github.com/ghunshoot/RTAB-Map-ROS-Kinect/blob/master/Img/4.png)
