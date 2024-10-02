.. _overview:
Hardware
########

This section includes an overview of the hardware components of Freddy 2.0

.. _hardware_components:

Hardware Components
===================

- **Base**: The base of the robot consists of the wheels, the EtherCAT board, the power button and the charging port. It also has a switch to connect different devices and the PMU board.

- **Torso**: The torso of the robot consists of the arms, the ethernet switch, ehternet port, the power button and the emergency button.

- **Arms**: The arms of the robot are connected to the torso via ethernet cables.

- **Power Management Unit (PMU)**: The PMU board is responsible for controlling the power supply to the wheels and the arms.

- **Emergency Button (RE5910)**: The wireless emergency stop device is used to enable/disable the power supply to the robot.

.. _communication_architecture:

Communication Architecture
=========================

- Individual wheels are connected to the EtherCAT board which his further connected to the switch at the base of the robot. Similarly, the ethernet cables from the individual arms are connected to a switch at the torso of the robot. 

- The power supply to the wheels and the arms are controlled by the PMU board.

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

Method1: Hold the power button the the base of the robot until it starts blinking and then release it.

Method2: Send the SHUTDOWN command to the PMU board. This is further discussed in the section describing the commands to control the power of the robot.

.. _charging_the_robot:
Charging the Robot
==================

Connect the charger to the charging port on the robot's base. The blinking green LED on the base of the robot indicates that the robot is charging. The robot can be charged while it is powered on or off.
