# pepperTeleoperation

System requirement
  Ubuntu 14.04
  ROS Indigo (##Install driver for ROS From ROS Wiki page(http://wiki.ros.org/openni_kinect))

#Kinect driver for Ubuntu 14.04 and ROS indigo
##Prerequisites Install dependencies below:
sudo apt-get install g++  
sudo apt-get install cmake cmake-gui  
sudo apt-get install doxygen  
sudo apt-get install mpi-default-dev openmpi-bin openmpi-common  
sudo apt-get install libflann1 libflann-dev  
sudo apt-get install libeigen3-dev  
sudo apt-get install libboost-all-dev  
sudo apt-get install libvtk5.8-qt4 libvtk5.8 libvtk5-dev  
sudo apt-get install libqhull*  
sudo apt-get install libusb-dev  
sudo apt-get install libgtest-dev  
sudo apt-get install git-core freeglut3-dev pkg-config  
sudo apt-get install build-essential libxmu-dev libxi-dev  
sudo apt-get install libusb-1.0-0-dev graphviz mono-complete  
sudo apt-get install qt-sdk openjdk-7-jdk openjdk-7-jre

##Install Kinect driver on Ubuntu
Install 3 drivers below:
OpenNI
Kinect Sener Module
NITE
These files can be downloaded from this git repo.

###Install OpenNI

cd ${YOURDOWNLOADPATH}/kinect_driver/OpenNI
cd Platform/Linux/CreateRedist
chmod +x RedistMaker
./RedistMaker
cd ../Redist/OpenNI-Bin-Dev-Linux-x64-v1.5.7.10
sudo ./install.sh
###Install Kinect Sensor Module

cd ${YOURDOWNLOADPATH}/kinect_driver/SensorKinect
cd Platform/Linux/CreateRedist
chmod +x RedistMaker
./RedistMaker
cd ../Redist/Sensor-Bin-Linux-x64-v5.1.2.1
chmod +x install.sh
sudo ./install.sh
###Install NITE

cd ${YOURDOWNLOADPATH}/kinect_driver/NITE
sudo ./install.sh

