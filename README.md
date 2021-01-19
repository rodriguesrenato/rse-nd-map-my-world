# rse-nd-map-my-world
Course project "Map My World" repository for the Udacity Robotics Software Engineer Nanodegree program.

This project contains the following Catkin packages :
* renato_robot: 
    * Implementation of a differential drive robot with lidar sensor and camera, written in URDF.
    * Contains a world called `restaurant_renato.world`.
    * RTab launch files for mapping and localization.
    * Screenshots of the results.
   
## Installation
Clone this repository in **src** folder in your catkin workspace and following repositories bellow:
```
cd ~/catkin_ws/src
git clone https://github.com/rodriguesrenato/rse-nd-map-my-world.git
cd rse-nd-map-my-world
git clone https://github.com/ros-teleop/teleop_twist_keyboard
sudo apt-get install ros-kinetic-rtabmap-ros
```

Download my rtabmap database from [here](https://drive.google.com/file/d/1rgNc-BGYRgWc_ZZ63NjMpQOD7OWC4Kb-/view?usp=sharing) and move it to `~/.ros`.

## Usage
Supposing your catkin workspace is located in `~/`, source your workspace:
```
cd ~/catkin_ws
catkin_make
source devel/setup.bash
```
Use the .launch files to launch packages in the following sequence:
* Terminal 1: `roslaunch renato_robot world.launch`.
* Terminal 2: `rosrun teleop_twist_keyboard teleop_twist_keyboard.py` and adjust both speeds to `0.12`.

For run localization with rtabmap.db I previously made:
* Terminal 3: `roslaunch renato_robot localization.launch`.
* Terminal 4: `rosrun rviz rviz` and add `Robot Model`,`map`,`laser scan` to check the results.

* Obs: To generate `.yaml` and `.pgm` files, you have to have previously launched `localization.launch` and `world.launch`, then open a new terminal and run `rosrun map_server map_saver -f myMap`. The files will be generated on your current folder. The `-f` param specify you map output name.

For mapping a new rtabmap.db:
* Terminal 3: `roslaunch renato_robot mapping.launch`.
* Use `teleop Terminal 2` to navigate through the map and do the same path 3 times.
* Hit `CTRL+C` on `Terminal 3` and save a copy of the `rtabmap.tb` located in `~/.ros`.
* Terminal 4: `rtabmap-databaseViewer ~/.ros/rtabmap.db` to see the results of mapping process.

## License
The contents of this repository are covered under the MIT License.
