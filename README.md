# ros_robotiq_urcap_control
Control our robotiq grippers (2F-85 and Hand-E) from ROS thru the Robotiq URCap on the e-series.

BASED ON: https://dof.robotiq.com/discussion/1962/programming-options-ur16e-2f-85#latest

ROS/Python2 port by felixvd  (use py3-master brach for Python3 and ROS noetic)

Messing around, SID and Hand-E testing by MOJO

ROS2 Jazzy port by Falken98

## Using this repository

1. Select the src folder in your desired workspace and download the repository\
    ```
    cd ros2_ws/src\
    git clone ROS2-jazzy https://github.com/frdedynamics/ros_robotiq_urcap_control.git 
    ```

2. Install required package dependencies
    ```
    rosdep update && rosdep install --ignore-src --from-paths src -y
    ```

3. Build your workspace
    ```
    cd ros2_ws
    colcon build --symlink-install
    ```

4. Running launch file
    ```
    ros2 launch ros2_robotiq_urcap_control ros2_robotiq_urcap_control.launch.py
    ```

5. You can test the node you started by opening a new terminal an run the following command
    ```
    ros2 topic pub /Robotiq2FGripperRobotOutput messages/msg/Robotiq2FGripperRobotOutput "{r_pr: 255, r_sp: 50, r_fr: 50}"
    ```