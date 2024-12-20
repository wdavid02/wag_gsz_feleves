# `wag_gsz_feleves` package
ROS 2 python package.  [![Static Badge](https://img.shields.io/badge/ROS_2-Humble-34aec5)](https://docs.ros.org/en/humble/)


## Packages and build


It is assumed that the workspace is `~/ros2_ws/`.


### Clone the packages
``` r
cd ~/ros2_ws/src
```
``` r
git clone https://github.com/wdavid02/wag_gsz_feleves
```

### Build ROS 2 packages
``` r
cd ..
```
``` r
colcon build --packages-select wag_gsz_feleves --symlink-install
```

<details>
<summary> Don't forget to source before ROS commands.</summary>

``` bash
source ros2_ws/src/install/setup.bash && source install/setup.bash
```
</details>


<details>
<summary> You'll need some packages to download or upgrade</summary>

``` bash
sudo apt install ros_humble_gazebo_ros_pkgs
```
``` bash
sudo apt install ros-humble-ros2-control ros-humble-ros2-controllers ros-humble-gazebo-ros2-control
```
``` bash
sudo apt install ros-humble-slam-toolbox
```

</details>


Split the pane. In the first pane we start the simulation, Gazebo and Rviz2 with the following row:
``` r
ros2 launch wag_gsz_feleves launch_sim.launch.py

```


### Control panel
You'll be able to control the robot with your keyboard in the second pane
``` r
ros2 run teleop_twist_keyboard teleop_twist_keyboard

```

## Original project

The foundational idea for the project and much of the initial guidance 
    were drawn from the following source: https://articulatedrobotics.xyz/.

However, as the project progressed, I strived to rely increasingly on my own ideas, 
especially since differences in ROS versions often made it impractical to directly 
replicate the original implementation.



<details>
<summary>Error possibility</summary>

``` bash
If you want to control the bot, the teleop pane must be active instead of Gazebo. Click there to activate it.
```
</details>