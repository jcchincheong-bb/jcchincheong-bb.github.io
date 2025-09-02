---
layout: log
title: 4.0 Braking Investigations
date: 16-06-2025
project: Vehicle Dynamics Simulations
main-image: /assets/image%2079.png
excerpt: Investigating braking behviour with and without an ABS control system
---

---
### 4.0.1 Specifications

![image.png](/assets/image%2073.png)

![image.png](/assets/image%2074.png)

### 4.0.2 Parameters

![image.png](/assets/image%2075.png)

MB = 5350

Optimal slip = 13%, Controller Gain 20000

### 4.1.0 Formulation

### 4.1.1 Simulink Models

![w/o ABS](/assets/image%2076.png)

w/o ABS

![w/ ABS](/assets/image%2077.png)

w/ ABS

![ABS Controller](/assets/image%2078.png)

ABS Controller

![image.png](/assets/image%2079.png)

![image.png](/assets/image%2080.png)

![image.png](/assets/image%2081.png)

### 4.2.0 Simulation Results for w/o ABS

![Stopping Distance](/assets/image%2082.png)

Stopping Distance

![Slip (to 1s)](/assets/image%2083.png)

Slip (to 1s)

![Slip (to 2s)](/assets/image%2084.png)

Slip (to 2s)

![Slip (to 10s)](/assets/image%2085.png)

Slip (to 10s)

### 4.2.1 Simulation Results for w/ ABS

![Very strange error occurs when vehicle speed approaches 1 m/s. The wheel speed plummets (indicating it is locked) and then the slip jumps to 1 and the vehicle deceleration decreases slightly](/assets/image%2086.png)

Very strange error occurs when vehicle speed approaches 1 m/s. The wheel speed plummets (indicating it is locked) and then the slip jumps to 1 and the vehicle deceleration decreases slightly

![Disabling zero cross detection also makes it so that the wheel speed overtakes the vehicle speed at one point and we get negative slip. We also observe some numerical errors](/assets/image%2087.png)

Disabling zero cross detection also makes it so that the wheel speed overtakes the vehicle speed at one point and we get negative slip. We also observe some numerical errors

![w/o zero crossing detection](/assets/image%2088.png)

w/o zero crossing detection

![w/ zero crossing detection](/assets/image%2089.png)

w/ zero crossing detection

---