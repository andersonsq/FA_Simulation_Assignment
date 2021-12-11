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
* [Part 1: Plant Layout Design and Simulation](#part-1:-plant-layout-design-and-simulation)
* [Part 2: Robot Simulation](#part-2:-robot-simulation)
* [Links](#links)

## Part 1: Plant Layout Design and Simulation

### Evaluation:

[x]Import the parts model provided as mesh (obj files in the link section Page 3)
[x]Based on the size of the parts, setup the conveyors (4 in total, 1 in and 3 out)
[x]Setup the floor shop like adding enclosures, modifying the visual aspects.
[x]Program the motion of the conveyor
[x]Program a conveyor to spawn parts with sensors
[x]Make your mechanism with at least basic shapes
[x]Program your mechanism to identify the target with a vision sensor (color coding is fine)
[]Program the mechanism to pick and place the parts in the right conveyor

## Part 2: Robot Simulation

1. Based on your requirement of workspace from your previous setup, select a type of mechansim and formulate its DH/MDH parameters. (more workspace is better)
2. From your MDH parameters, draw the schematic representation. 
3. Model necessary files in any CAD software of your choice and export it as OBJ 
4. Using OOPs strategy, assemble your mechanism in CoppeliaSim.
5. Choose an appropriate gripper for all three parts 
6. Implement the inverse kinematics using the built in simIk API
7. Implement Pick and place logic using trajectory planning. 
8. Extend the logic above to pick the part an place it in the right conveyor

## Links

The spawmning parts were built using [Mesh parts page](https://unigeit.sharepoint.com/:f:/r/sites/FLEXIBLEAUTOMATION2021/Documenti%20condivisi/ModelForSimulationAssignment?csf=1&web=1&e=B9YCQ1).
