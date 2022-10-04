# Laboratory 3

Seongmin Jung  
Professor Lee  
ECSE 373  
03 October 2022  

---

This project is for learning and implementing rosbag.

## `launch` files

### 1. `original.launch`

This launch file is for running the robot model from previous lab.

    $ roslaunch my_navvis original.launch use_xacro:=true use_robot_state_publisher:=true

`use_xacro` argunemt is for deciding whether to use `xacro` file or `urdf` file. If this argument is `true`, rviz will use `base.xacro` file of previous lab. Unless, rviz will use `base.urdf` file of previous lab.
There is one more argument, `use_robot_state_publisher`, inside this launch file. If this argument is `true`, `robot_state_publisher` and `joint_state_publisher_gui` node is started. Unless, `static_transform_publisher` will be used.

### 2. `new.launch`

This launch file is for running newer robot model, where `base_link` and `imu` is added. You can select which one to use between newer and older model by argument `use_previous_launch`.

    $ roslaunch my_navvis original.launch use_xacro:=true use_robot_state_publisher:=true use_previous_launch:=false

There is one more argument in addition to the `original.launch` file, `use_previous_launch`. If this argument is `true`, the robot model from `navvis_description` package will be used. Unless, newer model from this package will be used.

### 3. `new2.launch`

This launch file is for displaying map and laser scanning result at rviz

    $ roslaunch my_navvis original.launch use_xacro:=true

There is one more argument, `bag_path`. this argument is the location of the bag file. The map file should be played by rosbag in seperate terminal.

    $ rosbag play --clock ~/Desktop/glennan_5_complete.bag /tf_trajectory:=/tf


---

I referred to the instruction of Laboratory #3 in ECSE 373 class.