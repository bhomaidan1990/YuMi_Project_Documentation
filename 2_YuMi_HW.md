# 2.2 The Interface with the PC

---

## 2.2.1 Introduction

The package `yumi_hw` is the responsible package for the Robot-PC interfacing with the YuMi ROS Server, it depends on `industrial-core` package, and namely `simple_messages`.

---

### Nodes

1. `yumi_hw_ifce_node.cpp`

2. `yumi_gripper_node.cpp`


### Topics

1. `gripper_state`

### Messages

### Services

1. `YumiGrasp.srv` uint16, the gripper id: {left:1, right:2}.

### Additional configuration

This library also defines some configuration parameters for EGM/RWS connections to the YuMi Robot in `egm_rws_config.yaml`.

---

## 2.2.2 Technical Details

### Headers

1. `yumi_hw.h`, this header file defines the class `YumiHW` which defines some statistics and data-types.
2. `yumi_hw_rws.h`, this header files defines the RWS connection using the classes:
    - `YumiJointStateHandler`, which Overrides message handler, and keeps joint states thread-safe.
    - `YumiRapidInterface`, which Keeps a connection to the robot and sends and receives joint states.
3. `yumi_hw_egm.h`, this header file defines the EGM connection using a private repositories (we don't have access to it):
`abb_rws_interface`, and `abb_egm_interface`.
4. `yumi_hw_gazebo.h`, This header file defines the class `YumiHWGazebo` to simulate the Robot using Gazebo.
5. `yummi_gripper_node.h`, this header file defines the classes:
    - `YumiGripperStateHandler`, which Keeps a connection to the grippers and sends and receives joint states.
    - `YumiGripperNode`, which handles the topics `grasp_request`, and `grasp_release`.

### Source Files

1. `yumi_hw.cpp`, this source file defines a YuMi HW Interface with the ROS Server on YuMi.
2. `yumi_hw_rws.cpp`, this source file just calls the corresponding header.
3. `yumi_hw_egm.cpp`, this source file is dependant on the repository `abb_egm_interface`, which is private!.
4. `yumi_hw_gazebo.cpp`, this class is to simulate the cobot behaviour on Gazebo.
5. `grippers_hw.cpp`, this source file publishes the topic `gripper_state`.
6. `yumi_hw_iface_node.cpp`, this source file creates a YuMi HW Interface with the ROS Server on YuMi using RWS.
7. `yummi_gripper_node`, this script is the main method of the `yumi_rws_gripper_node` file.