# Quadcopter Simulation
> This project aims to visualize a Quadcopter's motion (roll, pitch, yaw, and hover) in 3D space by adjusting the speed of four motors using Python. The project consists of three main parts: motor speed adjustment window, dynamic calculation, and 3D visualization. Special thanks to [this MATLAB script](https://youtu.be/4hlQ2pf842U?si=a1AfHnj8r89j6BRX) for finding the Quadcopter's equation of motion.
# Table of Contents
> - [**Installation**](#installation)
> - [**Component**](#component)
> - [**User Guide**](#userguide)
> - [**Demos & Result**](#demosnresult)
> - [**Conclusion**](#conclusion)
> - [**Reference**](#reference)
## Installation <a name="installation"></a>

### Pygame

1. Open Visual Studio Code.
2. Go to the terminal or open a new terminal.
3. Copy and paste the following command:
   ```bash
   pip install pygame
   ```
4. Press Enter and wait for the download to complete.

### OpenGL

1. Open Visual Studio Code.
2. Go to the terminal or open a new terminal.
3. Copy and paste the following command:
   ```bash
   pip install PyOpenGL
   pip install PyOpenGL_accelerate
   ```
4. Press Enter and wait for the download to complete.

### Numpy

1. Open Visual Studio Code.
2. Go to the terminal or open a new terminal.
3. Copy and paste the following command:
   ```bash
   pip install numpy
   ```
4. Press Enter and wait for the download to complete.
   
# Component <a name="component"></a>
> - **Motor Slider**
> Description
> 
> - **Dynamic Calculation**
> >
> - **3D Visualization**
> >The visualization part involves drawing the Quadcopter on the screen and updating its position based on differential values of X, Y, Z, roll, pitch, yaw.
> //Add picture
> > ![a](https://ibb.co/GdqvMGP)
> > <img src="https://ibb.co/GdqvMGP"/> 
> >The libraries used for this visualization are Pygame for display creation and OpenGL for graphics rendering.
# User Guide <a name="userguide"></a>
> Description
# Demos & Result <a name="demosnresult"></a>
> Description
# Conclusion <a name="conclusion"></a>
> Description
# Reference <a name="reference"></a>
> - [1] DRONE OMEGA, 2020, What is a Quadcopter Explained Thoroughly [Online], Available: https://droneomega.com/what-is-a-quadcopter/ [02/11/23]
> - [2] Pranav Bhounsule, 2020, Robotics Lec25,26: 3D quadcopter, derivation, simulation, animation (Fall 2020) [Online], Available: https://www.youtube.com/watch?V=4hlq2pf842u [02/11/23]
> - [3] MATLAB, 2020, Drone Simulation and Control, Part 1: Setting Up the Control Problem [Online], Available: https://www.youtube.com/watch?V=hgcgpuqb67q [02/11/23]
> - [4] Lebedev, A. (2013). Design and Implementation of a 6DOF Control System for an Autonomous Quadrocopter (Master's thesis). Julius Maximilian University of Würzburg, Faculty of Mathematics and Computer Science, Aerospace Information Technology, Chair of Computer Science VIII, Prof. Dr. Sergio Montenegro.
