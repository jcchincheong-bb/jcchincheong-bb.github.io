To add another project, just copy paste any folder and edit the content. The main project page is the index.md file.
The most important content in this file is the pre-amble:
```
---
layout: post
title: Planar Multibody Dynamics Simulations
description: Creating a general purpose simulation software for planar multibody dynamics in MATLAB.
github: https://github.com/jcchincheong-bb/MBD_Simulations
skills: 
  - MATLAB
  - Multibody Dynamics
  - Numerical Methods
main-image: /DAS.png
timeline:
  - April 2025|Newton-Raphson Method using Symbolic Math
  - May 2025|Kinematic Joint Constraint Functions
  - June 2025|Generalised Scripts for Coordinate Setup, Constraint Formulation and Kinematic Analysis
---
```

To add logs, just create another md file with a preamble as follows

```
---
layout: log
title: Success in Syms Implementation
date: 03-05-2025
project: Planar Multibody Dynamics Simulations
main-image: /4BL.PNG
excerpt: Used MATLAB Syms tool box to generalise NR method
---
```

Make sure the main index file and log files are in the root of the project folder. Also, if you create a sub folder for images, then you need to absolute references to include them. 

Also, you can use the general project template:
```
# Overview

## 🔧 Current Features

## 📦 Requirements

## 🚧 Future Work

## 📚 References
LAST NAME, First Name. *Title*. Publisher, YYYY.
```