# pepperTeleoperation

System requirement

  Ubuntu 14.04
  
  ROS Indigo (##Install driver for ROS From ROS Wiki page(http://wiki.ros.org/openni_kinect))
  
  Openni
  
  Kinnect camera
  
  Pepper robot

# 1.  Kinect driver for Ubuntu 14.04 and ROS indigo

sudo apt-get install ros-kinetic-openni-camera ros-kinetic-openni-launch

sudo apt-get install git build-essential python libusb-1.0-0-dev freeglut3-dev openjdk-8-jdk

sudo apt-get install doxygen graphviz mono-complete

## Install OpenNI

cd ~/ mkdir kinect

cd ~/kinect 

git clone https://github.com/OpenNI/OpenNI.git 

cd OpenNI 

git checkout Unstable-1.5.4.0 cd Platform/Linux/CreateRedist 

chmod +x RedistMaker 

./RedistMaker

cd /yourpath/kinect/OpenNI/Platform/Linux/Redist/OpenNI-Bin-Dev-Linux-x64-v1.5.4.0 

sudo ./install.sh

cd ~/kinect 

git clone https://github.com/avin2/SensorKinect 

cd SensorKinect 

cd Platform/Linux/CreateRedist 

chmod +x RedistMaker 

./RedistMaker

cd /yourpath/kinect/SensorKinect/Platform/Linux/Redist/Sensor-Bin-Linux-x64-v5.1.2.1 

chmod +x install.sh 

sudo ./install.sh

## Install Ros indigo OpenNI

sudo apt-get install ros-indigo-openni*

## Install NITE

cd ~/kinect 

git clone https://github.com/arnaud-ramey/NITE-Bin-Dev-Linux-v1.5.2.23 

cd /yourpath/kinect/NITE-Bin-Dev-Linux-v1.5.2.23/x64 

sudo ./install.sh

## Install openni_tracker

cd ~/catkin_ws/src 

git clone https://github.com/ros-drivers/openni_tracker.git

## Remake Catkin Workspace

cd ~/catkin_ws 

catkin_make 

catkin_make install

## launch openni and openni_tracker

roscore

roslaunch openni_launch openni.launch

rosrun image_view image_view image:=/camera/rgb/image_color

rosrun image_view disparity_view image:=/camera/depth_registered/disparity

cd ~/catkin_ws/devel 

source setup.bash 

rosrun openni_tracker openni_tracker

## create package

roscreate-pkg kinect_pj rospy tf

cd ~/yourpath/catkin_ws/src/kinect_pj/src 

chmod +x kinect_pj

## launch kinect_pj

cd ~/catkin_ws/devel 

source setup.bash 

rosrun kinect_pj kinect_pj

# 2.  Run the teleoperation command
Rename these files into kinect_pj under the kinect_pj/src folder. Change the permission to executable by use chmod 777 filename

open multiple terminal to run the commands below:

roscore

roslaunch openni_launch openni.launch

rosrun openni_tracker openni_tracker

#manually change the option in 'Fixed Frame' under 'Global Options' to visualize Openni Tracker

rosrun rviz rviz

#check the ip and port in choreograph tool for the virtual machine, rename kinect_pj(copyAndPlay)V3 or kinect_pj(liveSimu)v3 into kinect_pj to determine which one to run

rosrun kinect_pj kinect_pj --ip <ip> --port <port>


Reference:

https://github.com/ros-drivers/openni_tracker/issues/9

https://github.com/cltl/pepper/wiki/Installation

https://github.com/ketchart/Pepper-Robot-controlled-by-Kinect-in-Ubuntu


