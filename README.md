# Quadcopter Simulation
> This project aims to visualize a Quadcopter's motion (roll, pitch, yaw, and hover) in 3D space by adjusting the speed of four motors using Python. The project consists of three main parts: motor speed adjustment window, dynamic calculation, and 3D visualization. Special thanks to [this MATLAB script](https://youtu.be/4hlQ2pf842U?si=a1AfHnj8r89j6BRX) for finding the Quadcopter's equation of motion.
# Table of Contents
 - [**Installation**](#installation)
 - [**Component**](#component)
 - [**User Guide**](#userguide)
 - [**Demos & Result**](#demosnresult)
 - [**Conclusion**](#conclusion)
 - [**Future plan**](#futureplans)
 - [**Reference**](#reference)
 
## Installation <a name="installation"></a>

### Pygame

> 1. Open Visual Studio Code.
> 2. Go to the terminal or open a new terminal.
> 3. Copy and paste the following command:
>    ```bash
>    pip install pygame
>    ```
> 4. Press Enter and wait for the download to complete.

### OpenGL

> 1. Open Visual Studio Code.
> 2. Go to the terminal or open a new terminal.
> 3. Copy and paste the following command:
>    ```bash
>    pip install PyOpenGL
>    pip install PyOpenGL_accelerate
>    ```
> 4. Press Enter and wait for the download to complete.

### Numpy

> 1. Open Visual Studio Code.
> 2. Go to the terminal or open a new terminal.
> 3. Copy and paste the following command:
>    ```bash
>    pip install numpy
>    ```
> 4. Press Enter and wait for the download to complete.
   
# Component <a name="component"></a>
### Motor Slider
> In motor slider UI have 4 component
> > 1. The text shows the speed of all 4 motors in RPM units.
The lowest value is 0 and the highest is 20,000 rads/s
> > 2. Slide bar is used only for adjusting the speed of individual motors in order of Left is the least value.  The right is the most valuable.
> > 3. Text box is used to override the speed of all motors to have the same speed.
> > 4. Enter button is used to confirm the override of the motor speed after entering the speed into the text box.
The value will not be changed immediately. You must press the Enter key under the text box or press Enter on your keyboard.
>
> ![image](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/5093bfe2-c106-442c-87ed-3b0b97bffe91)
>
> The speed is adjusted by interacting with the UI in one way or another. The motor speed value is stored through
An array variable with 4 fields, going from index 0 as the 1st motor to index 3 as the 4th motor.
>
> There are 2 main libraries used:
> > 1. os, which is a library that increases the convenience of cross-program development.
platform by allowing the program to have access to certain functions so that it can be used with the operating system
of the computer
> > 2. Pygame, which is a library for developing games using the Python language as the main language
> The creator has applied it for user interaction through UI and simulation.

### Dynamic Calculation
> 1. Quadcopter Degree of Freedom
> 2. Quadcopter Degree of Freedom
> 3. Quadcopter Dynamics
> >  - External force and torque
> >  - Equation of Motion (EOM)
> > >How to solve equations to find The equations of motion of the quadcopter are therefore applied by the Euler-Lagrange Method, where the Lagrangian (L) is the difference between the kinetic energy (K.E.) and the gravitational potential energy (P.E.).
```math
\vec{F}_{ext} = R_{rpy}
\begin{bmatrix} 0 \\ 0 \\ k\left(\sum_{i=1} ^4 w_i^2 \right) \end{bmatrix} - \begin{bmatrix} A_{x}\dot{x} \\ A_{y}\dot{y} \\ A_{z}\dot{z} \end{bmatrix}
```

```math
\vec{t}_{ext} = \begin{bmatrix} t_{x} \\ t_{y} \\ t_{z} \end{bmatrix}
= \begin{bmatrix} t_{\phi} \\ t_{\theta} \\ t_{\phi} \end{bmatrix}
= \begin{bmatrix} lk\left(w_4^2 - w_2^2\right) \\ lk\left(w_3^2 - w_1^2\right) \\ b\left(w_1^2 + w_2^2 + w_3^2 + w_4^2\right)\end{bmatrix}
```
> > > When $A_{n}$ is damper
> > > 
```math
R_{rpy} = R_{z}\left(\psi\right)R_{y}\left(\theta\right)\thetaR_{x}\left(\phi\right)
```
> > >
> 
### 3D Visualization
> The visualization part involves drawing the Quadcopter on the screen and updating its position based on differential values of X, Y, Z, roll, pitch, yaw.
> 
> ![messageImage_1702377397219](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/99a2c0b9-bafe-4758-93dd-eee1ea889626)

> ![messageImage_1702377463885](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/197dc99a-d1ea-4d05-9998-150636515228)

> The libraries used for this visualization are Pygame for display creation and OpenGL for graphics rendering.
> 
# User Guide <a name="userguide"></a>
> 1. Within the Jupyter Notebook file, there are a total of 3 sections, consisting of:
> > - Section 1: Importing relevant packages into the project.
```ruby
from Input_GUI import MotorSpeedSliders
from QuadcopterDynamics import QuadcopterDynamics
from Visualization_v1 import Quadcopter3DVisualization, QuadcopterController
import time
import numpy as np
import math
```
> > ![image2](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/7d426e6b-f197-482a-9667-7975c474550e)

> > - Section 2 : The part where various parameters of the quadcopter are adjusted, using SI units. The adjustments should be made before clicking the "Run" button.

> > ![image3](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/02722073-d31d-413b-80ae-3a79f5680797)

> > - Section 3 : Main loop witch operating at a frequency of 100 Hz.
> > ![image4](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/cf3f2d33-8aad-4fad-ae70-2e3f5895b01e)

> 2.  After clicking 'Run All,' the window as shown in the picture will appear.
> > ![image6](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/cbb31498-3bb7-4ba6-9dae-6bdebc348cf7)

> > After adjusting the speed of each motor successfully, press 'Start Sim' to enter the Visualization page.
> > ![image7](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/739a7a89-5762-4d03-bc7b-674a23047a7a)

> 3.  When visualization is complete, Program will shut down automatically.

# Demos & Result <a name="demosnresult"></a>
## Examples
> - Example 1: falling and spin about z-axis
>   
https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/f8c78fa3-a352-4a3c-b3cf-c508be4a07e9

> - Example 2: hover and spin about z-axis
> 
https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/dcd746c1-80fc-45e8-a3b5-ec25d120da76

### Validation
> - Animation compare with MATLAB
> > spin about z-axis
> > 
https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/c9a7a609-692d-4733-9779-8c53a8ceec56

> > spin about x-axis
> > 
https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/8194b8d3-2021-4189-b823-29aa6c514485

> - Dynamic compare with MATLAB
> > Spin about z-axis and hover
> > ![image5](https://github.com/Fzil0n/QuadCopter_simulation/assets/122668877/289444ca-9cde-4c84-b460-13a33d8b735d)

# Conclusion <a name="conclusion"></a>
> Simulating the motion of a quadcopter using Python can be done using various libraries available in Python, such as NumPy, Matplotlib, and others, to model the dynamics of the quadcopter and visualize the results graphically. Comparing the results to MATLAB may show some differences depending on the simulation methods and parameters used in each system. However, by choosing appropriate parameters and using accurate simulation methods, you can achieve results that closely match those in MATLAB.
> 
> To enhance the reliability of your testing, you can experiment with refining and adjusting the parameters of the Python simulation to obtain results that closely align with the MATLAB outcomes. Testing that involves comparing results with MATLAB is a good step to verify the accuracy and reliability of your simulation.
> 
> Keep in mind that since there is no real-world quadcopter for direct comparison, testing can only be done by comparing results within the simulation environments, such as Python and MATLAB.

# Future plan <a name="futureplans"></a>
> - **Improve GUI and visualization.**
> - **Testing with real quadcopter.**
> - **Real-time speed adjustment and display of results.**
# Reference <a name="reference"></a>
> - [1] Lebedev, A. (2013). Design and Implementation of a 6DOF Control System for an Autonomous Quadrocopter (Master's thesis). Julius Maximilian University of Würzburg, Faculty of Mathematics and Computer Science, Aerospace Information Technology, Chair of Computer Science VIII, Prof. Dr. Sergio Montenegro.
> - [2] DRONE OMEGA, 2020, What is a Quadcopter Explained Thoroughly [Online], Available: [droneomega.com](https://droneomega.com/what-is-a-quadcopter/) [02/11/23]
> - [3] Pranav Bhounsule, 2020, Robotics Lec25,26: 3D quadcopter, derivation, simulation, animation (Fall 2020) [Online], Available: [YouTube](https://www.youtube.com/watch?v=4hlq2pf842u) [02/11/23]
> - [4] MATLAB, 2020, Drone Simulation and Control, Part 1: Setting Up the Control Problem [Online], Available: [YouTube](https://www.youtube.com/watch?v=hgcgpuqb67q) [02/11/23]
> - [5] Kanishke Gamagedara (2021). Plotting 3D Objects with Matplotlib. Github. https://github.com/kanishkegb/pyplot-3d
> - [6] P. Wang, Z. Man, Z. Cao, J. Zheng and Y. Zhao, "Dynamics modelling and linear control of quadcopter," 2016 International Conference on Advanced Mechatronic Systems (ICAMechS), Melbourne, VIC, Australia, 2016, pp. 498-503, doi: 10.1109/ICAMechS.2016.7813499.
> - [7] Ahmad, F., Kumar, P., & Patil, P. P. (2018). Modeling and simulation of a quadcopter with altitude and attitude control. Nonlinear Studies, 25(2), 287–299.
