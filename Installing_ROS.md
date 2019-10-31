## Ros Installation
First we start checkmarking all in System Settings > Software and Updates > Ubuntu Software, Other Software, and Updates.
Also in Ubuntu Software we select `Download from: Main`. Notice when close the window it will start updating the cache. When finish updating it bring back "Failed to download repository information", ignore and go on.
IMAGES 

In terminal.
Setup your sources.list.
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
Set up your keys.
```
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```
```
sudo apt-get update

sudo apt-get install -f

sudo apt-get install ros-kinetic-desktop-full

sudo rosdep init
rosdep update

echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential

catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3 -DPYTHON_INCLUDE_DIR=/usr/include/python3.7m -DPYTHON_LIBRARY=/usr/lib/libpython3.7m.so
```
