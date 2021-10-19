# 2.3 Description of YuMi
> The joint numbering for each arm follows ABB's strange convention, 
> namely (in physical order starting with the joint connecting to the body): **1, 2, 7, 3, 4, 5, 6**
---

## 2.3.1 Introduction

The physical description of YuMi is spitted into three packages:
1. `yumi_description`.
2. `yumi_support`.
3. `yumi_control`


---

## 2.3.2 YuMi Description

This package uses `xarco` to generate the description of the robot.
It includes two folders: 
- **meshes**, which includes the meshes necessary for the robot description.
- **urdf**, which contains the *xarco* files necessary to generate the **Unified Robotic Description Format (URDF)** files.

---

## 2.3.3 YuMi Support

This is a modified driver from the ROS-Industrial [abb driver](https://github.com/ros-industrial/abb_driver). 
Main changes are for handling the two arms of YuMi in a reasonable manner.
The original package is part of the **ROS-Industrial** program and contains nodes for interfacing with ABB industrial robot controllers.

This package holds in the `config` file the `joint_names` for the `left`, and the `right` arms, in addition to a launch file called `robot_interface.launch`, this file in turn loads the config file contents, and runs the following nodes:
- **abb_driver/robot_state** for left, and right arms.
- **abb_driver/motion_download_interface** for left, and right arms.
- **industrial_robot_client/joint_trajectory_action** for left, and right arms.
- **topic_tools/xxxx_joints_relay** for left, and right arms.
- **industrial_robot_client/joint_trajectory_action** for left, and right arms.
- **yumi_hw/yumi_gripper_node**.

---

## 2.3.4 YuMi Control

This package is mainly a set of configurations:
1. `gripper_controllers.yaml`, it defines **Effort gripper controllers**, and **Effort gripper position controllers**.
2. `position_controllers.yaml`, it defines the Joints, and the states for publishing.
3. `traj_controllers.yaml`, it defines the position/velocity for the trajectory controller.
4. `velocity_controllers.yaml`, it defines the `Joint Velocity Controller` parameters.

---