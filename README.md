# Simulation Assignment of the Flexible Automayion course (Robotics Engineering / JEMARO, Unige)
The package contains the files and the simulation scenes for segregating car parts in a simulation environment.

A car engine parts manufacturer approaches you seeking a robotic automated solution for one of their problem in their loading and unloading station. The station receives three parts of the engine. The job of the station is to segregate the products and load it to the appropriate loading line. 
Your task is to design a flexible manufacturing cell (FMC) with robot centered layout for the above function. The design should handle the requirements below.

1. Ability to supply multiple vendors at the same time
2. Fully automated solution from product in to out
3. Flexible in terms of volume and mix product handling
4. Zero-defect product

Your solution must also take into account the practicalities like accessibility of robots and tools for maintenance, repair, and cleaning. Safety features like enclosures and a separate control station. Following the successful design and implementation of the simulation, you must also provide two reports: one including the technical implementation details and assumptions made in developing the simulation, and the other for the client to prove that your solution works and convince them it is a good idea to implement your solution.

## Table of contents
* [Part 1: Plant Layout Design and Simulation [3 pts]](#part-1:-plant-layout-design-and-simulation-[3-pts])
* [General info](#general-info)
* [Part 2: Robot Simulation [15 pts]](#part-2:-robot-simulation-[15-pts])
* [Part 3: Analysis and Optimization of the cell](#part-3:-analysis-and-optimization-of-the-cell) 
* [Part 4: Report Generation](#part-4:-report-generation) 
* [Links](#links)

## Part 1: Plant Layout Design and Simulation [3 pts]

1. Import the parts model provided as mesh (obj files in the link section Page 3)
2. Based on the size of the parts, setup the conveyors (4 in total, 1 in and 3 out)
3. Setup the floor shop like adding enclosures, modifying the visual aspects.
4. Program the motion of the conveyor.
5. Program the in conveyor to spawn one of the three parts in random (consecutive spawning of the same part is allowed too for a maximum of 2 iterations)

## General info



## Part 2: Robot Simulation [15 pts]

1. Based on your requirement of workspace from your previous setup, select a type of mechansim and formulate its DH/MDH parameters. (more workspace is better)
2. From your MDH parameters, draw the schematic representation. 
3. Model necessary files in any CAD software of your choice and export it as OBJ 
4. Using OOPs strategy, assemble your mechanism in CoppeliaSim.
5. Choose an appropriate gripper for all three parts 
6. Implement the inverse kinematics using the built in simIk API
7. Implement Pick and place logic using trajectory planning. 
8. Extend the logic above to pick the part an place it in the right conveyor

## Links

Model of the engine parts:
```
https://unigeit.sharepoint.com/:f:/r/sites/FLEXIBLEAUTOMATION2021/Documenti%20condivisi/ModelForSimulationAssignment?csf=1&web=1&e=B9YCQ1
```

