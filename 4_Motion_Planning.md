# 2.4 Motion Planning

---

## 2.4.1 Introduction

The package concerning this part is: `yumi_moveit_config`, it uses **OMPL** through **MoveIt**, and **RViz**, and depends on `yumi_decribtion` package.
It has mainly two folders:
1. **launch** contains launch files, and accompanying `xml`  configurations, and **config** folder which stores some important parameters:

### Launch folder

- `default_warehouse_db.launch`, optional warehouse_db (doesn't exist), and launches `warehouse.launch` file.
- `warehose,launch`, through accompanying `xml` file it defines the port `33829`, in addition to other warehouse settings.
- `demo*.launch`, these set of launch files for demo, and not real robot interaction. <!-- TODO: Explain them in details -->
- `gazebo.launch`, for the same past purpose. <!-- TODO: Explain in details -->
- `joystick_control.launch`, joystick plugin for moveIt.
- `move_group.launch`, moveit, and planning scene parameters defined here.
- `moveit_rviz.launch`, to launch `rviz`, and load the `kinematics.yaml` file.
<!-- TODO: do the rest -->

### Config folder

- `controllers.yaml`, this file defines the `FollowJointTrajectory`, which is very important to the other packages.
<!-- TODO: do the rest -->