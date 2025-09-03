---
layout: log
title: First Attempt at coding Newton Raphson Method
date: 25-04-2025
project: Planar Multibody Dynamics Simulations
main-image: /4BL.PNG
excerpt: Tried writing Matlab code to solve it by hard Coding NR multivariable method
---

---
# Development
{% include image-gallery.html images="4BL.PNG" height="400"%}

Derived kinematic constraint equations for the classic four bar linkage

{% include image-gallery.html images="4BL-constraints.PNG" height="400"%}

Attempted to solve by hand analytically 

{% include image-gallery.html images="4BL-manual-computation.png" height="400"%}

Tried writing Matlab code to solve it by hard Coding NR multivariable method


Code:
```matlab
%% Parameters 
a = 2.0;
b = 0.5;
l1 = 1.0;
l2 = 3.0;
l3 = 2.2;

%% Equations
phi1 = @(O1,O2,O3)(l1*cos(O1)+l2*cos(O2)+l3*cos(O3)-a);
phi2 = @(O1,O2,O3)(l1*sin(O1)+l2*sin(O2)+l3*sin(O3)-b);
phi3 = @(O1,t)(O1-pi/2-2*pi*t);
fO1 = @(t)(pi/2 + 2*pi*t);  % function to find O1 at given time t 

%% Solving using NR Multivariable method (scratch)
O1 = pi/2; % for t=0 in phi3
theta0 = [O1;0.4;0.6]; % initial guess
theta1 = theta0 - inv(jacobian(theta0(1),theta0(2),theta0(3)))*[phi1(theta0(1),theta0(2),theta0(3));phi2(theta0(1),theta0(2),theta0(3));phi3(theta0(1),0)];
theta1
%% Functions
function [D] = jacobian(O1,O2,O3)
		l1 = 1.0;
    l2 = 3.0;
    l3 = 2.2;
    D = [-l1*sin(O1) -l2*sin(O2) -l3*sin(O3);l1*cos(O1) l2*cos(O2) l3*cos(O3);1 0 0];
end
```

# Sources
{% include image-gallery.html images="kehrein-NR.png" height="400"%}
<span style="font-size: 10px">"[Kehrein, Primer for Numerics]"</span>  

{% include image-gallery.html images="brandt-NR.png" height="400"%}
<span style="font-size: 10px">"[Brandt, 2909 Multibody Dynamics]"</span> 

---