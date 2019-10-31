# RTAB-Map in ROS with Kinect Xbox-360

Ubuntu 16.04
## Installation
## Ros Installation
First we start checkmarking all in System Settings > Software and Updates > Ubuntu Software, Other Software, and Updates.
Also in Ubuntu Software we select `Download from: Main`. Notice when close the window it will start updating the cache. When finish updating it bring back "Failed to download repository information", ignore and go on.
IMAGES 

In terminal.
Setup your sources.list
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

Set up your keys
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654

sudo apt-get update

sudo apt-get install -f

sudo apt-get install ros-kinetic-desktop-full

sudo rosdep init
rosdep update

echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

sudo apt install python-rosinstall python-rosinstall-generator python-wstool build-essential

catkin_make -DPYTHON_EXECUTABLE=/usr/bin/python3 -DPYTHON_INCLUDE_DIR=/usr/include/python3.7m -DPYTHON_LIBRARY=/usr/lib/libpython3.7m.so

## Installation of RTAB map Linux
```
$ sudo apt-get update
$ sudo apt-get install -f
$ sudo apt-get install libsqlite3-dev libpcl-dev libopencv-dev git cmake libproj-dev libqt5svg5-dev libsuitesparse-dev
$ sudo apt-get install -f
```
/////////////////////////////

poniendo todos los checkmarks


libfreenect
en CMakeLists.txt
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}  -std=c++11")

Installing g2o
```
$ git clone https://github.com/RainerKuemmerle/g2o.git 
$ cd g2oe
$ mkdir build
$ cd build
$ cmake -DBUILD_WITH_MARCH_NATIVE=OFF -DG2O_BUILD_APPS=OFF -DG2O_BUILD_EXAMPLES=OFF -DG2O_USE_OPENGL=OFF ..
$ make -j4
$ sudo make install
```

Installing GTSAM
```
$ git clone --branch 4.0.0-alpha2 https://github.com/borglab/gtsam.git gtsam-4.0.0-alpha2
$ cd gtsam-4.0.0-alpha2
$ mkdir build
$ cd build
$ cmake -DGTSAM_USE_SYSTEM_EIGEN=ON -DGTSAM_BUILD_EXAMPLES_ALWAYS=OFF -DGTSAM_BUILD_TESTS=OFF -DGTSAM_BUILD_UNSTABLE=OFF ..
$ make -j4
$ sudo make install
```
Installing RTAB-Map
```
$ git clone https://github.com/introlab/rtabmap.git rtabmap
$ cd rtabmap/build
$ cmake ..
$ make -j4
$ sudo make install
$ ldconfig
```
## Installation of RTAB map MacOs
https://apple.stackexchange.com/questions/208478/how-do-i-disable-system-integrity-protection-sip-aka-rootless-on-macos-os-x



sudo add-apt-repository ppa:linuxuprising/java

sudo apt-get update

sudo apt-get install oracle-java13-installer

sudo apt-get install graphviz
sudo apt-get install doxygen
