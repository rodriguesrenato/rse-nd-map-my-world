# rse-nd-project-3
Course project "Map My World" repository for the Udacity Robotics Software Engineer Nanodegree program.

This project contains the following Catkin packages :
* renato_robot: 
    * Implementation of a differential drive robot with lidar sensor and camera, written in URDF.
    * Contains a world called `restaurant_renato.world`.
   
## Installation
Clone this repository in **src** folder in your catkin workspace and following repositories bellow:
```
cd ~/catkin_ws/src
git clone https://github.com/rodriguesrenato/rse-nd-map-my-world.git
cd rse-nd-map-my-world
git clone https://github.com/ros-teleop/teleop_twist_keyboard
```


## Usage
Supposing your catkin workspace is located in `~/`, source your workspace:
```
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```
Use the .launch files to launch packages in the following sequence:
* Terminal 1: `roslaunch renato_robot world.launch`

## License
The contents of this repository are covered under the MIT License.
