---
layout: log
title: 3.0 Quarter Car Model
date: 29-05-2025
project: Vehicle Dynamics Simulations
main-image: /assets/image%2014.png
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

![image.png](/assets/image%2013.png)

![image.png](/assets/image%2014.png)

### 3.0.0.3 Assumptions

### 3.0.0.4 Parameters

![image.png](/assets/image%2015.png)

### 3.0.1.0 Formulation of Differential Equations

![image.png](/assets/image%2016.png)

![image.png](/assets/image%2017.png)

![image.png](/assets/image%2018.png)

### 3.0.1.1 Final Equations

### 3.0.1.2 Simulink Models

![Simulink Model for Quarter Car with Road Excitation](/assets/image%2019.png)

Simulink Model for Quarter Car with Road Excitation

### 3.0.1.3 Laplace Transform

![image.png](/assets/image%2020.png)

![image.png](/assets/image%2021.png)

### 3.0.2.0 Observations from Parameter Modification w/o Road Excitation

![image.png](/assets/image%2022.png)

![200 kg less](/assets/image%2023.png)

200 kg less

![40000 N/m more](/assets/image%2024.png)

40000 N/m more

![3000 damping more](/assets/image%2025.png)

3000 damping more

![400000 spring 3000 damping](/assets/image%2026.png)

400000 spring 3000 damping

![10 stiffness](/assets/image%2027.png)

10 stiffness

![15 damping](/assets/image%2028.png)

15 damping

### 3.0.2.1 Observations from Frequency Modification

![with the integrator](/assets/image%2029.png)

with the integrator

![with the derivative](/assets/image%2030.png)

with the derivative

![image.png](/assets/image%2031.png)

![2 rad/s](/assets/image%2032.png)

2 rad/s

![3 rad/s](/assets/image%2033.png)

3 rad/s

![4 rad/s](/assets/image%2034.png)

4 rad/s

![5 rad/s](/assets/image%2035.png)

5 rad/s

![6 rad/s](/assets/image%2036.png)

6 rad/s

![7 rad/s](/assets/image%2037.png)

7 rad/s

![7.071 rad/s Natural frequency ](/assets/image%2038.png)

7.071 rad/s Natural frequency 

![8 rad/s](/assets/image%2039.png)

8 rad/s

![9 rad/s](/assets/image%2040.png)

9 rad/s

![10 rad/s](/assets/image%2041.png)

10 rad/s

![10 rad/s](/assets/image%2042.png)

10 rad/s

![2, 4, 6, 8, 10 Hz](/assets/image%2043.png)

2, 4, 6, 8, 10 Hz

![2 Hz](/assets/image%2044.png)

2 Hz

![5 Hz](/assets/image%2045.png)

5 Hz

![8 Hz](/assets/image%2046.png)

8 Hz

![10 Hz](/assets/image%2047.png)

10 Hz

![2 Hz, 5s](/assets/image%2048.png)

2 Hz, 5s

![5 Hz, 5s](/assets/image%2049.png)

5 Hz, 5s

![8 Hz, 5 secs](/assets/image%2050.png)

8 Hz, 5 secs

![10 Hz, 5 s](/assets/image%2051.png)

10 Hz, 5 s

![100 Hz](/assets/image%2052.png)

100 Hz

### 3.0.2.2 Frequency Domain Characteristics

![From using Simulink ](/assets/image%2053.png)

From using Simulink 

![From using bode()](/assets/image%2054.png)

From using bode()

![Psuedo Bode Plot of Amplitude (z [m] vs w [rad/s] )](/assets/image%2055.png)

Psuedo Bode Plot of Amplitude (z [m] vs w [rad/s] )

![Pseudo Bode Plot of Phase ](/assets/image%2056.png)

Pseudo Bode Plot of Phase 

## 3.1.0 Quarter Car Two Mass Model

Similar to 3.0.0, this section extends the Quarter Car Model to the dual mass variation, focusing on frequency domain characteristics and parameterisation.

### 3.1.1.? Transfer Functions

$$
G_{B_{acc}}(s)=\frac{k_W k_Bs^4+(k_W c_B+k_B c_W)s^3+c_W c_Bs^2}{m_{B}m_{W}s^{4}+[m_{B}(k_{B}+k_{W})+m_{W}k_{B}]s^{3}+[m_{B}(c_{B}+c_{W})+m_{W}c_{B}+k_{B}k_{W}]s^{2}+[k_{B}c_{W}+k_{W}c_{B}]s^{3}+c_{B}c_{W}}
$$

$$
G_{W_{acc}}(s)=\frac{m_B k_Ws^5+(k_W k_B+m_B c_W)s^4+(k_Bc_W+k_W c_B)s^3+c_Bc_Ws^2}{m_{B}m_{W}s^{4}+[m_{B}(k_{B}+k_{W})+m_{W}k_{B}]s^{3}+[m_{B}(c_{B}+c_{W})+m_{W}c_{B}+k_{B}k_{W}]s^{2}+[k_{B}c_{W}+k_{W}c_{B}]s^{3}+c_{B}c_{W}}
$$

![image.png](/assets/image%2057.png)

### 3.1.2.? Frequency Domain Characteristics

![image.png](/assets/image%2058.png)

### 3.1.2.? Wheel Mass Variation

![image.png](/assets/image%2059.png)

![image.png](/assets/image%2060.png)

### 3.1.2.? Tire Stiffness Variation

![image.png](/assets/image%2061.png)

![image.png](/assets/image%2062.png)

![tirestiffness_var_acc_100-200kN-m.png](/assets/tirestiffness_var_acc_100-200kN-m.png)

![tirestiffness_var_force_100-200kN-m.png](/assets/tirestiffness_var_force_100-200kN-m.png)

### 3.1.2.? Body Stiffness Variation

![image.png](/assets/image%2063.png)

![image.png](/assets/image%2064.png)

### 3.1.2.? Body Damping

![image.png](/assets/image%2065.png)

![image.png](/assets/image%2066.png)

![image.png](/assets/image%2067.png)

![image.png](/assets/image%2068.png)

### 3.1.2.? Body Mass Variation

![image.png](/assets/image%2069.png)

![image.png](/assets/image%2070.png)

![image.png](/assets/image%2071.png)

![image.png](/assets/image%2072.png)

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