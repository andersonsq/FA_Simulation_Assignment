# Simulation Assignment of the Flexible Automayion course (Robotics Engineering / JEMARO, Unige)
The package contains the files and the simulation scenes for segregating car parts in a simulation environment.

A car engine parts manufacturer approaches you seeking a robotic automated solution for one of their problem in their loading and unloading station. The station receives three parts of the engine. The job of the station is to segregate the products and load it to the appropriate loading line. 
Your task is to design a flexible manufacturing cell (FMC) with robot centered layout for the above function. The design should handle the requirements below.

1. Ability to supply multiple vendors at the same time
2. Fully automated solution from product in to out
3. Flexible in terms of volume and mix product handling
4. Zero-defect product

Your solution must also take into account the practicalities like accessibility of robots and tools for maintenance, repair, and cleaning. Safety features like enclosures and a separate control station.

## Table of contents
* [Part1:Plant layout design and simulation](#part1:plant-layout-design-and-simulation)
* [Robot simulation](#robot-simulation)
* [Links](#links)

## Plant layout design and simulation

### Evaluation:

- [x] Import the parts model provided as mesh (obj files in the link section Page 3)
- [x] Based on the size of the parts, setup the conveyors (4 in total, 1 in and 3 out)
- [x] Setup the floor shop like adding enclosures, modifying the visual aspects.
- [x] Program the motion of the conveyor
- [x] Program a conveyor to spawn parts with sensors
- [x] Make your mechanism with at least basic shapes
- [x] Program your mechanism to identify the target with a vision sensor (color coding is fine)
- [ ] Program the mechanism to pick and place the parts in the right conveyor

## Robot simulation

- [x] **Based on your requirement of workspace from your previous setup, select a type of mechansim and formulate its DH/MDH parameters. (more workspace is better)**

### MATLAB code for the DH
```
%Foward Kinematic for ABB Robot Porte Outil
 
J0=(0*pi)/180; J1=(0*pi)/180; J2=(0*pi)/180;     
d0=1300+100; d1=100+300+50; d2=-300;                                                       
                                                                                                     
alpha0=(90*pi)/180; alpha1=(-90*pi)/180; alpha2=(0*pi)/180; 

N_of_links = ['J0';'J1';'J2'];
Teta_deg = [J0;J1;J2];                       
Translation = [d0;d1;d2];
Alpha = [alpha0;alpha1;alpha2];
 
T = table(N_of_links,Teta_deg,Alpha,Translation)
```
```
%% STEP 1 BASE -> J1
 
%Base J0 -> J1 
%Translation d0
%Rotation J0 around Z
 
DH0 = [cos(J0) -cos(alpha0)*sin(J0)    sin(alpha0)*sin(J0)     0*cos(J0);
       sin(J0)  cos(alpha0)*cos(J0)   -sin(alpha0)*cos(J0)     0*sin(J0);
       0        sin(alpha0)            cos(alpha0)             d0;
       0        0                      0                       1];
 ```
 ```
 %% Step 2 J1 -> J2
 
%J1 -> J2
%Translation d1
%Rotation J1 around Z
 
DH1 = [cos(J1) -cos(alpha1)*sin(J1)    sin(alpha1)*sin(J1)    0*cos(J1);
       sin(J1)  cos(alpha1)*cos(J1)   -sin(alpha1)*cos(J1)    0*sin(J1);
       0        sin(alpha1)            cos(alpha1)            d1;
       0        0                      0                      1];
```
``` 
%% Step 3 J2 -> EE
 
%J2 -> EE
%Translation d2
%Rotation J3 around Z
 
DH2 = [cos(J2) -cos(alpha2)*sin(J2)    sin(alpha2)*sin(J2)   0*cos(J2);
       sin(J2)  cos(alpha2)*cos(J2)   -sin(alpha2)*cos(J2)   0*sin(J2);
       0        sin(alpha2)            cos(alpha2)           d2;
       0        0                      0                     1];
```
``` 
%% Fowars Kinematic combined
 
EE = DH0*DH1*DH2
```
![](scenes/DH_robot.png)

- [x] **From your MDH parameters, draw the schematic representation.** 

| Joints  |  Theta (θ°)  | Alpha (α°)  |  a (mm)|  d (mm)
| ------------------- | ------------------- | ------------------- | ------------------- | ------------------- 
|  Base -> Link1 |  θ1° |   90° |  0 |  1400 
|  Link1 -> Link2 |  θ2° |  -90° |  0 |  450  
|  Link2 -> EE |  θ3° |    0° |  0 |  -300  

![](scenes/DH_collumn.png)

- [x] \(Optional) Model necessary files in any CAD software of your choice and export it as OBJ 
- [x] Using OOPs strategy, assemble your mechanism in CoppeliaSim.
- [x] Choose an appropriate gripper for all three parts 
- [x] Implement the inverse kinematics using the built in simIk API
- [ ] Implement Pick and place logic using trajectory planning. 
- [ ] Extend the logic above to pick the part an place it in the right conveyor

## Links

The spawmning parts were built using [Mesh parts page](https://unigeit.sharepoint.com/:f:/r/sites/FLEXIBLEAUTOMATION2021/Documenti%20condivisi/ModelForSimulationAssignment?csf=1&web=1&e=B9YCQ1).
