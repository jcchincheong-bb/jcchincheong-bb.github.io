---
layout: log
title: Success in Syms Implementation
date: 03-05-2025
project: Planar Multibody Dynamics Simulations
main-image: /4BL.PNG
excerpt: Used MATLAB Syms tool box to generalise NR method
---

---
# Development
I tested out using syms with the NR logic:
```matlab
%% Reset
clear;   % resets all the variables since syms can be a bit fucky wucky

%% Equations 
m = 2;                     % number of variables 
syms x [m 1]               % syms variable array
% syms F(x)                  % syms function definition
F(x) = [-2*cos(x1)+3*cos(x2);10*sin(x1)+15*sin(x2)-18];   % function array (test from Num Math Chp 6)
D = jacobian(F,x);       % Jacobian matrix

%% Parameters
% x_in = input('What is your guess?'); % intial guess
x_in = [0.59;0.99];
n = 0; % number of steps
n_max = 10; % step timeout
tol = 1e-15;  % tolerance for successful zero

%% Solving 
x_sol = zeros([m 1]);
x_sol = x_in;              % setting the initial guess 
f_out = subs(F,x,x_sol(:,1));    % evaluating the inital guess function value
df_out = subs(D,x,x_sol(:,1));   % evaluating the inital guess jacobian value
ep = sum(double(f_out));         % error
while (abs(ep)>=tol) && (n<n_max)
    x_sol(:,n+2) = x_sol(:,n+1) - (inv(df_out) * f_out);    % NR Method multivariable 
    f_out = subs(F,x,x_sol(:,n+2));                         % update function value
    df_out = subs(D,x,x_sol(:,n+2));                        % update jacobian
    ep = sum(double(f_out));                                % update the error
    n = n+1;
end
x_out = vpa(x_sol)
```
Then I developed this NR function script for ease of use:
```matlab
function [n,xout] = NRfunc(F,x,x_in,tol,n_max)
    D = jacobian(F,x);                        % Jacobian matrix
    x_sol = x_in;                             % setting the initial guess 
    n = 0;                                    % number of steps
    f_out = subs(F,x,x_sol(:,1));             % evaluating the inital guess function value
    df_out = subs(D,x,x_sol(:,1));            % evaluating the inital guess jacobian value
    ep = sum(double(f_out));                  % error
    while (abs(ep)>=tol) && (n<n_max)
        x_sol= x_sol - (inv(df_out) * f_out); % NR Method multivariable 
        f_out = subs(F,x,x_sol);              % update function value
        df_out = subs(D,x,x_sol);             % update jacobian
        ep = sum(double(f_out));              % update the error
        n = n+1;                              % update the steps
    end
    xout = vpa(x_sol);                       % send output
end
```
Here is the function used with the four bar linkage:
```matlab
%% System Parameters 
a = 2.0;
b = 0.5;
l1 = 1.0;
l2 = 3.0;
l3 = 2.2;
m = 3;
syms t
syms O [m 1]

%% Equations
phi(O) = [l1*cos(O1)+l2*cos(O2)+l3*cos(O3)-a; ...
    l1*sin(O1)+l2*sin(O2)+l3*sin(O3)-b;...
    O1-pi/2];

%% Solution Parameters 
O_in = [pi/2;0.4;0.6];  % initial guess
n_max = 10;             % max steps
tol = 1e-15;  % tolerance for successful zero

%% Solution
[n,xout] = NRfunc(phi,O,O_in,tol,n_max);
fprintf("In %d steps\n",n)
disp(xout)
```

~~Not working, not sure why. Gonna try hard coding it in.~~ 

I noticed the computations and conversions between syms and double are what are causing the long wait time. 

I also tried using fsolve to check my answers:
```matlab
%% Parameters 
a = 2.0;
b = 0.5;
l1 = 1.0;
l2 = 3.0;
l3 = 2.2;

%% Equations
phi = @(O)([l1*cos(O(1))+l2*cos(O(2))+l3*cos(O(3))-a; ...
    l1*sin(O(1))+l2*sin(O(2))+l3*sin(O(3))-b; ...
    O(1)-pi/2]);
%% Solving using NR Multivariable Method (fsolve)
theta0 = [pi/2;0.58;1.3]; % initial guess
fsolve(phi,theta0)
```

I also attempted to solve it analytically [https://de.mathworks.com/help/symbolic/solve-a-system-of-algebraic-equations.html]
```matlab
%% System Parameters 
a = 2.0;
b = 0.5;
l1 = 1.0;
l2 = 3.0;
l3 = 2.2;
m = 3;
syms t
syms O [m 1]

%% Equations
phi = [l1*cos(O1)+l2*cos(O2)+l3*cos(O3)-a==0; ...
    l1*sin(O1)+l2*sin(O2)+l3*sin(O3)-b==0;...
    O1-pi/2==0];

%% Solution
S = solve(phi,O);
num_sol_1 = double([S.O1(1);S.O2(1);S.O3(1)])
num_sol_2 = double([S.O1(2);S.O2(2);S.O3(2)])
```

# Sources
{% include image-gallery.html images="kehrein-NR.png" height="400"%}
<span style="font-size: 10px">"[Kehrein, Primer for Numerics]"</span>  

{% include image-gallery.html images="brandt-NR.png" height="400"%}
<span style="font-size: 10px">"[Brandt, 2909 Multibody Dynamics]"</span> 

---