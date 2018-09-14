# Robotics Nanodegree #

## Term2 – Project3: ROS Map My World Robot using RTAB-Map  ##

![](./media/caudaz_robotND2-proj3_x10speedup_15secs.gif)

### ABSTRACT ###


### INTRO ###


### INSTALLATING ROS ###

1. Install ROS:

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list' && sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116 && sudo apt-get update && sudo apt-get install ros-kinetic-desktop-full && sudo rosdep init && rosdep update && echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc && source ~/.bashrc
```
Note: Skip this step if ROS is already installed.

2. Install dependencies: 
```
sudo apt-get install ros-kinetic-rtabmap ros-kinetic-rtabmap-ros && sudo apt-get remove ros-kinetic-rtabmap ros-kinetic-rtabmap-ros
```

3. Install RTAB-Map: 
```
cd ~ && git clone https://github.com/introlab/rtabmap.git rtabmap && cd rtabmap/build && cmake .. && make && sudo make install
```

4. Create .gazebo folder: Open gazebo and then close it.

5. Add model collision adjustments: 
```
curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C ~/.gazebo/
```

6. For issues refer to:

https://classroom.udacity.com/nanodegrees/nd209/parts/dad7b7cc-9cce-4be4-876e-30935216c8fa/modules/aec2781f-e368-4e1e-9aef-d46aeee55354/lessons/0f504827-ab9c-4280-913f-413e4df602be/concepts/d83d9bd1-d7ff-4a61-85ce-bde660c71c2d
https://classroom.udacity.com/nanodegrees/nd209/parts/dad7b7cc-9cce-4be4-876e-30935216c8fa/modules/aec2781f-e368-4e1e-9aef-d46aeee55354/lessons/0f504827-ab9c-4280-913f-413e4df602be/concepts/bb19e9b7-9314-47c7-9afc-e23ce2811f7e

7- RTAB
```
sudo apt-get install ros-kinetic-rtabmap-ros
```

### RUNNING ROS ###

0) Create a Catkin workspace and download files

```
mkdir -p ~/catkin_ws/src

cd ~/catkin_ws/src

catkin_init_workspace

git clone https://github.com/caudaz/robotND2-proj3

cd ~/catkin_ws

catkin_make

```

1) Launch the gazebo world and your robot.
```
cd catkin_ws
source devel/setup.bash
roslaunch slam_project world.launch
```

2) Launch your teleop node.
```
cd catkin_ws
source devel/setup.bash
roslaunch slam_project teleop.launch
```

3) Launch your mapping node.
```
cd catkin_ws
source devel/setup.bash
roslaunch slam_project mapping.launch
```

4) Launch Rviz.
```
cd catkin_ws
source devel/setup.bash
roslaunch slam_project rviz.launch
```

5) Grab the rtabmap.db file from the ~/.ros/ directory and visualize it using the RTAB Map Database Viewer



UDACITY provided files:
----------------------
https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/Student+Project+Materials.zip
kitchen_dining.world -> worlds\
robot_slam.rviz      -> launch\config\
rtab_run             -> src\
rviz.launch          -> launch\
teleop               -> src\


