---
layout: post
title: Planar Multibody Dynamics Simulations
description: Creating a general purpose simulation software for planar multibody dynamics in MATLAB.
skills: 
  - MATLAB
  - Multibody Dynamics
  - Numerical Methods
main-image: /DAS.png
---

---
[GitHub](https://github.com/jcchincheong-bb/MBD_Simulations)

A general purpose simulator for the kinematics and dynamics of two dimensional multibody systems. 

Heavily inspired by the work of Javad N. Nikravesh, **Planar Multibody Dynamics**. I started it as part of a course on multibody dynamics in my university Hoschule Rhein-Waal, but I have since continuously improved it. Unlike Nikravhesh, this project uses the MATLAB symbolic toolbox to generalise formulations and also increases the accuracy of calculations at a marginal decrease in speed. 

## 🔧 Current Features
- Core functions for dynamics using the **body coordinate formulation**  
  *(see the `Functions/` directory)*
- General-purpose scripts for simulating multibody systems  
  *(see the `BC_Formulation/` directory)*
- Example simulations of two mechanisms from Nikravesh's text

## 📦 Requirements
- MATLAB R2018b or later
- Symbolic Math Toolbox 

## 🚧 Future Work
- Implementation of kinetic analyses (e.g., forward and inverse dynamics)
- Additional examples and validation cases
- More Animations
  
## 📚 References
NIKRAVESH, Parviz. *Planar Multibody Dynamics: Formulation, Programming with MATLAB®, and Applications*. CRC Press, 2007.
---
