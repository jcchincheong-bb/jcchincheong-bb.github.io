---
layout: post
title: Interpolation Calculator
description: Designing a automatic calculator which can calculate and plot the cubic splines and interpolated polynomials of a given set of univariate data.
skills: 
  - MATLAB
  - Multibody Dynamics
  - Numerical Methods
main-image: /Example_9DataPoints.jpg
---

---
[GitHub](https://github.com/jcchincheong-bb/Interpolation_Calculators)
Calculators for spline and polynomial interpolation

Inspired by the lectures of [Prof. Dr. Achim Kehrein](https://www.hochschule-rhein-waal.de/en/user/7351) on Numerical Mathematics. 

## 🔧 Current Features
- Cubic spline interpolation from a set of data points (either clamped or natural, just change the flag variable)
- Polynomial interpolation from a set of data points (using [Newton's Approach](https://en.wikipedia.org/wiki/Newton_polynomial))
- Plots of both interpolations on the same axes for comparison
- Polynomial interpolation of 3 points (using [Lagrange's Approach](https://en.wikipedia.org/wiki/Lagrange_polynomial)) in Python

{% include image-gallery.html images="Example_9DataPoints.jpg" height="400"%}
<span style="font-size: 10px">"Example with 9 Data Points"</span>  

## 📦 Requirements
- MATLAB R2018b or later
- Python (only for Lagrange Interpolater)

## 🚧 Future Work
- Implementing cubic spline and newton interpolaters in Python and generalising the lagrange interpolater.
  
## 📚 References
Kehrein, K. A Primer On Numerical Mathetmatics For Scientists and Engineers. _(unreleased, TBA)_
---
