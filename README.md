Spring 2020, California State University of Chico

Project Managers: Marshall Ellis, Reese Culbertson, Ryan Martinez 

### Table of Contents
- [1. Introduction](#1-Introduction)
- [2. Modeling](#2-Modeling)
- [3. Sensor Calibration](#3-Sensor_Calibration)
- [4. Controller Design and Simulations](#4-Controller_Design_and_Simulations)
- [5. Appendix A: Simulation Code](#5-Appendix_A:_Simulation_Code)
- [6. References](#6-References)

## 1. Introduction
The Furuta Pendulum consists of a driven arm which rotates in the horizontal plane and a pendulum attached to that arm which is free to rotate in the vertical plane. The goal of the project is to use a control system to balance a beam up vertically by controlling the motors position on a gantry. There are 2 encoders that measure the 360 degree position of the motor and the angle of the beam with respect to the floor. The system will keep the beam upright and prevent it from falling by moving to the location needed to balance the beam using a 90 degree angle. This project is purely virtual therefore, our group used MATLAB and MATLAB's SIMULINK to demonstrate the inverted pendulum project with linear and non-linear control algorithms. To display how the project works virtually, the program CoppeliaSim was used which the Furuta Pendulum was created and programmed with the MATLAB code we created.

## 2. Modeling

The control dynamics of the Furuta Pendulum project was implemented using CoppeliaSim. CoppeliaSim is a program which allows users to create projects and systems online and compute dynamic properties which helps give a virtual view of the systems workings.
The Matlab code the group created was connected with coppelia. Due to program issues and such, in the end we couldn’t get the virtual pendulum to stay up but we tried our best to be able to get the pendulum going!

#### Controller Calculations:

#### Variables :
	
x = position of arm

θ = angle of pendulum with respect to ground

F = applied force

m = mass of pendulum

l = length of pendulum 

g = gravity

fo = coefficient of friction

With two degrees of freedom the following equations are produced by the system:

##### Figure 1: Displays the system's model

![](meca482pendulumpicof%20modeling.JPG)


##### Figure 2: Displays the control theory model of the Furuta Pendulum

![](meca482controltheorymodel.JPG)

##### Figure 3: Displays the Simulink model for the Furuta Pendulum
![](Gifofsim.gif) 

----------------------------------------------------------------------------------
## 3. Sensor Calibration
There was no sensor calibration for this project due to the entirety of the project being virtual.

-----------------------------------------------------------------------------------------------------
## 4. Controller Design and Simulation

##### Figure 4: Image of the Furuta Pendulum designed using Coppelia

![](Meca482%20coppelia%20pic.JPG)

Simulation can be seen in action on github labeled "2011214247_received_240794620526014_1832625.mp4" (was having difficulty uploading the video onto the actual website)

-----------------------------------------------------------------------------------------------------

## 5. Appendix A: Simulation Code

##### State Space Representation:
![](StateSpaceRep_.JPG)

![](state%20space%20representation%20code%20continued.JPG)

![](state%20space%20representation%20code%20continued%20part%203.JPG)

##### Control FURPEN:
![](Control_FURPEN_.JPG)

--------------------------------------------------
## 6. References
1. Wikipedia, Furuta Pendulum, Retrieved by Feb., 25, 2020 from
https://en.wikipedia.org/wiki/Furuta_pendulum

2. Control System Tutorials for MATLAB and Simulink, Retrieved by Feb., 25, 2020 from
http://ctms.engin.umich.edu/CTMS/index.php?example=InvertedPendulum&section=SystemModeling

3.  Quanser, Rotary Inverted Pendulum, Retrieved by Jan, 27, 2020 from
https://www.quanser.com/products/rotary-inverted-pendulum/
