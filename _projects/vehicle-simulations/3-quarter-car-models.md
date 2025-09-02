---
layout: log
title: 3.0 Quarter Car Model
date: 29-05-2025
project: Vehicle Dynamics Simulations
main-image: /_projects/vehicle-simulations/assets/image-14.png
excerpt: Developing the Quarter Car modelling from ordinary differential equations to simulink model. Then extending the model to account for road disturbances. 
---

---
### 3.0.0.1 Specifications

Developing the Quarter Car modelling from ordinary differential equations to simulink model. Then extending the model to account for road disturbances. 

With the flat road model, investigating:

1. Response after a force step after 10 seconds
2. Response from parameter variation 

With the road excitation model, investigating:

1. Response for a sinusoidal excitation of 20mm at 2 Hz frequency.
2. Frequency domain characteristics 

### 3.0.0.2 Model Diagrams

![image.png](/_projects/vehicle-simulations/assets/image-13.png)

![image.png](/_projects/vehicle-simulations/assets/image-14.png)

### 3.0.0.3 Assumptions

### 3.0.0.4 Parameters

![image.png](/_projects/vehicle-simulations/assets/image-15.png)

### 3.0.1.0 Formulation of Differential Equations

![image.png](/_projects/vehicle-simulations/assets/image-16.png)

![image.png](/_projects/vehicle-simulations/assets/image-17.png)

![image.png](/_projects/vehicle-simulations/assets/image-18.png)

### 3.0.1.1 Final Equations

### 3.0.1.2 Simulink Models

![Simulink Model for Quarter Car with Road Excitation](/_projects/vehicle-simulations/assets/image-19.png)

Simulink Model for Quarter Car with Road Excitation

### 3.0.1.3 Laplace Transform

![image.png](/_projects/vehicle-simulations/assets/image-20.png)

![image.png](/_projects/vehicle-simulations/assets/image-21.png)

### 3.0.2.0 Observations from Parameter Modification w/o Road Excitation

![image.png](/_projects/vehicle-simulations/assets/image-22.png)

![200 kg less](/_projects/vehicle-simulations/assets/image-23.png)

200 kg less

![40000 N/m more](/_projects/vehicle-simulations/assets/image-24.png)

40000 N/m more

![3000 damping more](/_projects/vehicle-simulations/assets/image-25.png)

3000 damping more

![400000 spring 3000 damping](/_projects/vehicle-simulations/assets/image-26.png)

400000 spring 3000 damping

![10 stiffness](/_projects/vehicle-simulations/assets/image-27.png)

10 stiffness

![15 damping](/_projects/vehicle-simulations/assets/image-28.png)

15 damping

### 3.0.2.1 Observations from Frequency Modification

![with the integrator](/_projects/vehicle-simulations/assets/image-29.png)

with the integrator

![with the derivative](/_projects/vehicle-simulations/assets/image-30.png)

with the derivative

![image.png](/_projects/vehicle-simulations/assets/image-31.png)

![2 rad/s](/_projects/vehicle-simulations/assets/image-32.png)

2 rad/s

![3 rad/s](/_projects/vehicle-simulations/assets/image-33.png)

3 rad/s

![4 rad/s](/_projects/vehicle-simulations/assets/image-34.png)

4 rad/s

![5 rad/s](/_projects/vehicle-simulations/assets/image-35.png)

5 rad/s

![6 rad/s](/_projects/vehicle-simulations/assets/image-36.png)

6 rad/s

![7 rad/s](/_projects/vehicle-simulations/assets/image-37.png)

7 rad/s

![7.071 rad/s Natural frequency ](/_projects/vehicle-simulations/assets/image-38.png)

7.071 rad/s Natural frequency 

![8 rad/s](/_projects/vehicle-simulations/assets/image-39.png)

8 rad/s

![9 rad/s](/_projects/vehicle-simulations/assets/image-40.png)

9 rad/s

![10 rad/s](/_projects/vehicle-simulations/assets/image-41.png)

10 rad/s

![10 rad/s](/_projects/vehicle-simulations/assets/image-42.png)

10 rad/s

![2, 4, 6, 8, 10 Hz](/_projects/vehicle-simulations/assets/image-43.png)

2, 4, 6, 8, 10 Hz

![2 Hz](/_projects/vehicle-simulations/assets/image-44.png)

2 Hz

![5 Hz](/_projects/vehicle-simulations/assets/image-45.png)

5 Hz

![8 Hz](/_projects/vehicle-simulations/assets/image-46.png)

8 Hz

![10 Hz](/_projects/vehicle-simulations/assets/image-47.png)

10 Hz

![2 Hz, 5s](/_projects/vehicle-simulations/assets/image-48.png)

2 Hz, 5s

![5 Hz, 5s](/_projects/vehicle-simulations/assets/image-49.png)

5 Hz, 5s

![8 Hz, 5 secs](/_projects/vehicle-simulations/assets/image-50.png)

8 Hz, 5 secs

![10 Hz, 5 s](/_projects/vehicle-simulations/assets/image-51.png)

10 Hz, 5 s

![100 Hz](/_projects/vehicle-simulations/assets/image-52.png)

### 3.0.2.2 Frequency Domain Characteristics

![From using Simulink ](/_projects/vehicle-simulations/assets/image-53.png)

From using Simulink 

![From using bode()](/_projects/vehicle-simulations/assets/image-54.png)

From using bode()

![Psuedo Bode Plot of Amplitude (z [m] vs w [rad/s] )](/_projects/vehicle-simulations/assets/image-55.png)

Psuedo Bode Plot of Amplitude (z [m] vs w [rad/s] )

![Pseudo Bode Plot of Phase ](/_projects/vehicle-simulations/assets/image-56.png)

Pseudo Bode Plot of Phase 

## 3.1.0 Quarter Car Two Mass Model

Similar to 3.0.0, this section extends the Quarter Car Model to the dual mass variation, focusing on frequency domain characteristics and parameterisation.

### 3.1.1.? Transfer Functions

$$
G_{B_{acc}}(s)=\frac{k_W k_Bs^4+(k_W c_B+k_B c_W)s^3+c_W c_Bs^2}{m_{B}m_{W}s^{4}+[m_{B}(k_{B}+k_{W})+m_{W}k_{B}]s^{3}+[m_{B}(c_{B}+c_{W})+m_{W}c_{B}+k_{B}k_{W}]s^{2}+[k_{B}c_{W}+k_{W}c_{B}]s^3+c_{B}c_{W}}
$$

$$
G_{W_{acc}}(s)=\frac{m_B k_Ws^5+(k_W k_B+m_B c_W)s^4+(k_Bc_W+k_W c_B)s^3+c_Bc_Ws^2}{m_{B}m_{W}s^{4}+[m_{B}(k_{B}+k_{W})+m_{W}k_{B}]s^{3}+[m_{B}(c_{B}+c_{W})+m_{W}c_{B}+k_{B}k_{W}]s^{2}+[k_{B}c_{W}+k_{W}c_{B}]s^3+c_{B}c_{W}}
$$

![image.png](/_projects/vehicle-simulations/assets/image-57.png)

### 3.1.2.? Frequency Domain Characteristics

![image.png](/_projects/vehicle-simulations/assets/image-58.png)

### 3.1.2.? Wheel Mass Variation

![image.png](/_projects/vehicle-simulations/assets/image-59.png)

![image.png](/_projects/vehicle-simulations/assets/image-60.png)

### 3.1.2.? Tire Stiffness Variation

![image.png](/_projects/vehicle-simulations/assets/image-61.png)

![image.png](/_projects/vehicle-simulations/assets/image-62.png)

![tirestiffness_var_acc_100-200kN-m.png](/_projects/vehicle-simulations/assets/tirestiffness_var_acc_100-200kN-m.png)

![tirestiffness_var_force_100-200kN-m.png](/_projects/vehicle-simulations/assets/tirestiffness_var_force_100-200kN-m.png)

### 3.1.2.? Body Stiffness Variation

![image.png](/_projects/vehicle-simulations/assets/image-63.png)

![image.png](/_projects/vehicle-simulations/assets/image-64.png)

### 3.1.2.? Body Damping

![image.png](/_projects/vehicle-simulations/assets/image-65.png)

![image.png](/_projects/vehicle-simulations/assets/image-66.png)

![image.png](/_projects/vehicle-simulations/assets/image-67.png)

![image.png](/_projects/vehicle-simulations/assets/image-68.png)

### 3.1.2.? Body Mass Variation

![image.png](/_projects/vehicle-simulations/assets/image-69.png)

![image.png](/_projects/vehicle-simulations/assets/image-70.png)

![image.png](/_projects/vehicle-simulations/assets/image-71.png)

![image.png](/_projects/vehicle-simulations/assets/image-72.png)

### 3.1.3.? Discussion of Comfort and Safety

|  | Comfort | Safety | Conclusion |
| --- | --- | --- | --- |
| Wheel Mass | Improved for higher mass at frequency above wheel eigenfrequency | Less safe for higher mass at freq.  between the eigenfrequencies | Wheel mass needs to be **balanced**  |
| Tire Stiffness | Improved for lower stiffness for frequency above wheel eigenfrequency | Improved for lower stiffness at frequency above wheel eigenfrequency | Tire should be **soft** (but **hard enough to transfer** longitudinal and lateral **forces** and be durable) |
| Body Stiffness | Improved for lower stiffness near the body eigenfrequency | Improved for lower stiffness near the body eigenfrequency | Keep the stiffness **low** but **high enough to keep the wheels on the ground** and doesn't get completely compressed |
| Body Damping | Improved for higher damping at body eigenfrequency
Less for higher damping at frequencies above body eigenfrequency $\omega>\omega_B$ | Improved for higher damping at the two eigenfrequencies 
Less safe for higher damping between the eigenfrequencies  | We need to **consider** the excitation **frequency** |
| Body Mass | Improved for higher body mass at frequencies above body eigenfrequency | Less safe for higher mass at frequencies below the wheel eigenfrequency | **Balance** the body mass  |

---