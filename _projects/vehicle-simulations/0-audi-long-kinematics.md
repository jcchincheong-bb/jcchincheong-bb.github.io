---
layout: log
title: 0.0 Audi Longitudinal Kinematics
date: 25-04-2025
project: Vehicle Dynamics Simulations
main-image: /assets/image.png
excerpt: simulate accleration 0 - 60 kph (16.67 m/s)
---

---
### 0.0.1 Specifications

- We want to simulate accleration 0 - 60 kph (16.67 m/s)
    - plot a graph of speed vs time and see if the time is actually 6.7s
    - we use the data from the data sheet

### 0.0.2 Assumptions

1. No incline
2. Equilibrium at maximum speed 
3. Full electric vehicle → torque is constant 
4. Rolling resistance is constant and take maximum value for worst case scenario 
5. Tyre Class C1 w/ Fuel Efficiency class A [2] 
6. Negligble tyre deformation thoughout acceleration 
7. Road is dry 
8. Assume gear ratio is the same (not true but still)

### 0.0.3 Parameters

- Mass: $m = 2145 kg$ [1]
- Maximum torque $\mathcal{T}= 545 Nm$ [1] *3
- Maximum speed 112 mph $\dot{x}^{max}= 50.0685 m/s$  [1]
- Drag Factor $k_d=0.8233\frac{kg}{m}$
- Initial speed $\dot{x}_0=0 m/s$
- Tire diameter: $d=0.4953 m$ [2] *6
- $C_{rr}=0.0065$ [3], *4 *5
- Gear box ratio: $i=0.1$ [4] *8

### 0.1.0 Equations

$$
\ddot{x}=\frac{2\mathcal{T}}{d\cdot m\cdot i}-C_{rr}\cdot g-\frac{k_d \cdot\dot{x}^2}{m}  \quad (1)
$$

### 0.1.1 Simulation Model

### 0.2.0 Results

- We get around 40 m/s at 6.7s

### 0.3.0 Issues

- We failed to account for the driving slip which would have lowered the acceleration
- Gear box ratio could also hv degradation

### 0.4.0 Rework

![image.png](/assets/image.png)

Using the friction model of 1.0, we derived a new set of ODEs and formed the simulation as shown.

![image.png](/assets/image%201.png)

The results were much closer.

# Sources

1. Audi, Sport Q4 45 e-tron Datasheet
    
    ![image.png](/assets/image%2090.png)
    
    ![image.png](/assets/image%2091.png)
    
    ![image.png](/assets/image%2092.png)
    
2. Audi, Sport Q4 45 e-tron [Website](https://www.audi.co.uk/en/models/q4/q4-e-tron/configurator/?ulid=1743863220535&pr=F4BACM0_2025%7C5Y5Y%7CAO#layer=/uk/web/en/models/q4/q4-e-tron-overview.engine_infolayer.F4BA530PWEPYLWDM_2024.html)
    
    ![image.png](/assets/image%2093.png)
    
3. EU, Annex 1, Part A. Category C1 tyres (passenger car) of [Regulation (EU) 2020/740 of the European Parliament and of the Council of 25 May 2020 on the labelling of tyres with respect to fuel efficiency and other parameters](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=uriserv%3AOJ.L_.2020.177.01.0001.01.ENG&toc=OJ%3AL%3A2020%3A177%3ATOC)
    
    ![image.png](/assets/image%2094.png)
    
4. [Wikipedia](https://en.wikipedia.org/wiki/Audi_Q4_e-tron#:~:text=Its%201%2Dspeed%20gear%20is,a%20ratio%20of%2011.5%3A1.) * Needs to be vetted 

---