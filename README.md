# sensor_node

## Installation on a Raspberry PI

### Install Raspbian with Desktop
<https://www.raspberrypi.org/downloads/raspbian/>

### Enable SSH

1. Enter `sudo raspi-config` in a terminal window
* Select Interfacing Options
* Navigate to and select SSH
* Choose Yes
* Select Ok
* Choose Finish

### Enable VNC

1. Enter `sudo raspi-config` in a terminal window
* Select Interfacing Options
* Navigate to and select VNC
* Choose Yes
* Select Ok
* Choose Finish

### Change language and Time Settings

1. Enter `sudo raspi-config` in a terminal window
* Select Localisation Options
* Navigate to and select 'Change Locale'
* Select en_US.UTF8 UTF8 Enter
* Select Ok
* Choose Finish

### Change Timezone

1. Enter `sudo raspi-config` in a terminal window
* Select Localisation Options
* Navigate to and select 'Change Timezone'
* Navigate to and select 'Europe'
* Navigate to and select 'Amsterdam'
* Select en_US.UTF8 UTF8 Enter
* Choose Finish

### Install Software

## Install ROS
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
sudo apt-get update
sudo apt-get install -y python-rosdep python-rosinstall-generator python-wstool python-rosinstall build-essential cmake
sudo apt install dirmngr
sudo rosdep init
rosdep update
rosinstall_generator ros_comm --rosdistro kinetic --deps --wet-only --tar > kinetic-ros_comm-wet.rosinstall
wstool init src kinetic-ros_comm-wet.rosinstall
rosdep install -y --from-paths src --ignore-src --rosdistro kinetic -r --os=debian:stretch
sudo ./src/catkin/bin/catkin_make_isolated --install -DCMAKE_BUILD_TYPE=Release --install-space /opt/ros/kinetic -j2
source /opt/ros/kinetic/setup.bash
echo 'source /opt/ros/kinetic/setup.bash' >> ~/.bashrc
mkdir -p ~/catkin_workspace/src
cd catkin_workspace/src
catkin_init_workspace
cd ~/catkin_workspace/
catkin_make
source ~/catkin_workspace/devel/setup.bash
echo 'source ~/catkin_workspace/devel/setup.bash' >> ~/.bashrc
export | grep ROS
```
