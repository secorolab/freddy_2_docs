.. _setup:
Software Installation
#####################

.. _using_ros_middleware:
Using ROS 2
===========

The following packages are tested on ROS 2 Humble on Ubuntu 22.04. Please follow `ROS2 Humble installation <https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debs.html>`_ instructions, if you have not already installed ROS 2 on your system.

Setup Colcon Workspace
======================

  Colcon is the build system used by ROS 2. The following instructions to install colcon and creating a workspace 
  is referred from `this <https://docs.ros.org/en/humble/Tutorials/Beginner-Client-Libraries/Colcon-Tutorial.html>`_ link.

  **Installing Colcon**

  .. code-block:: bash

    sudo apt install python3-colcon-common-extensions

  **Creating a Workspace**

  .. code-block:: bash

    source /opt/ros/humble/setup.bash
    mkdir -p ~/ros2_ws/src
    cd ~/ros2_ws
    colcon build
    
  .. note::
    The *~/workspace_name/* directory (in the above example, it is *~/ros2_ws/*) is termed as **root** of the workspace. 
    In ROS2, while building the packages in a workspace, *colcon build* should be run from the root of the workspace.

Cloning Repositories
====================

  **kelo_interfaces** repository consists of the custom messages and services used in the project. **kelo_tulip** repository consists of the packages to control the robot.

  Clone both the repositories in the *src* directory of the workspace.

  .. code-block:: bash

    git clone git@github.com:secorolab/kelo_interfaces
    git clone -b ros2 git@github.com:secorolab/secorolab/kelo_tulip

  Build the packages and source the workspace

  .. code-block:: bash

    cd ~/ros2_ws
    colcon build
    source ~/ros2_ws/install/setup.bash

.. _ros_independent_installation:
ROS Independent Installation
===========================


git@github.com:secorolab/freddy_pmu_control.git








.. _powering_the_robot:
Powering the Robot
##################

.. _steps_to_power_on:
Steps to Power On
=================

Step1: Hold the power button on the base of the robot until the green LED turns on. Now the green LED light on the torso of the robot will start blinking and the red LED will turn on. This represents **safe mode**.

Step2: If not already done, pull the red coloured emergency button on the RE5910 and wait until the green LED on it to turn on. Now press the green button on the RE5910 and the same green LED will start blinking.

Step3: Now press the green button on the torso of the robot. The green LED on the torso will turn on and the red LED will turn off. This represents **operational mode** of the robot. Now the robot's wheels will by default get the power and are available for communication. To enable power supply to the arms, a command needs to be sent to the PMU board. This is further discussed in the section describing the commands to control the power of the robot.


.. _steps_to_power_off:
Steps to Power Off
==================

Method1: Hold the power button on the the base of the robot until it starts blinking and then release it.

Method2: Send the SHUTDOWN command to the PMU board. This is further discussed in the section describing the commands to control the power of the robot.

.. _charging_the_robot:
Charging the Robot
==================

Connect the charger to the charging port on the robot's base. The blinking green LED on the base of the robot indicates that the robot is charging. The robot can be charged while it is powered on or off.