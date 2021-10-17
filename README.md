# YuMi_Project_Documentation
> Documentation of the setup used to move the robot YuMi IRB 14000 using ROS

---

## 1. Overview

There are mainly **3 Repositories** for **3 Universities** who have a real additions to the **YuMi using ROS**:
> Note that there are no recent support for these repositories.
1. [Orebro University](https://github.com/OrebroUniversity/yumi): The pioneers in the implementation with YuMi ROS.
2. [KTH University](https://github.com/kth-ros-pkg/yumi): Their packages are the best(in my opinion), they have also camera using FTP package.
3. [ETH Institute](https://github.com/ethz-asl/yumi): They have facilitated the implementation and added many options.
    >  ETH has many branches, `addition/Demo` is the best, and they have a trial for implementing **Pick/Place** with YuMi in `yumi-stacking` branch.

Also there are some people who used a simulator (without setting up a real ROS Server on YuMi), as an example [yumi_simulator](https://github.com/dorianleveque/yumi-rws)
### Additional

There are some additions to the original code such as:
1. [Cartesian Velocity Controller using KDL library](https://github.com/JJHu1993/abb-yumi).
2. There is advanced implementation with sign language submitted [paper](http://arxiv.org/abs/2011.03914), [video](https://www.youtube.com/watch?v=jPvrAsN1Iwk&t=7s) to ICRA2021 [GitHub](https://github.com/liangyuwei/sign_language_robot.git).
3. There is some people who added their own world for simulation [example](https://github.com/DVNO911/cth_yumi).

## Miscellaneous

1. [RL using YuMi](https://github.com/0aqz0/yumi-gym)
2. [Simple EGM Control using Python](https://github.com/0aqz0/egm-control), [paper](https://arxiv.org/abs/2103.08882) [video](https://www.youtube.com/watch?v=wLlwYqFR55o)

---

## 2. Top-Level Architecture

---

The architecture in general is as follows:
- [2.1 YuMi ROS Server](1_YuMi_ROS_Server/Ros_Server.md) installed on YuMi.
- [2.2 Interface with the PC]() using `yumi_hw` package which depends on [simple_message](http://wiki.ros.org/simple_message) to form a standard industrial message.
- [2.3 Description of YuMi]() (Mesh and URDF etc...) `yumi_description`, and `yumi_control` to define the joints and the static parameters such as max speed and etc.
- [2.4 Motion Planning]() (MoveIt + OMPL + RViz) `yumi_moveit_config`.

---


