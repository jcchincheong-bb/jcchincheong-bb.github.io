---
layout: post
title: The Talking Mailbox
description: Designing and implementing a mailbox that can detect the presence of mail and email user.
github: https://github.com/AbhinavK02/LoRaProject
skills: 
  - Arduino
  - C++
  - Sensor Interfacing
  - LoRaWAN
  - LaTeX
main-image: /finalProduct_30deg.jpg
timeline:
  - November 2025|Design of Schematic and Selection of Components
  - December 2025|Implementation and Installation into Mailbox in HSRW
  - January 2026|Documentation and Report
---

---
# Overview
All people have a lot to do and may not always have time to check their mailbox. Imagine how long some letters are left in the mailbox for days just because one is too busy. On the other hand, checking your mailbox only to find nothing is quite frustrating. What if there was a way that your mailbox could tell you when there is mail? What if you had a talking mailbox? To solve this problem, we introduce The Talking Mailbox. The aim of The Talking Mailbox project is to design and assemble a system that can detect the presence of mail within a mailbox and notify the owner of the mailbox.

This project was done as part of the course 2907 Sensors and Actuator Networks at HSRW. It was completed alongside [Abhinav Kothari](https://www.linkedin.com/in/abhinav-kothari-2ak/). I did the sensor interfacing, microcontroller code and installation. He did the backend development including the implementation of a python server which decoded the payload and sent messages via email and an online dashboard. The full project report was written in LaTex and can be found [here](https://github.com/AbhinavK02/LoRaProject/blob/main/Project%20Report%20-%20Talking%20Mailbox.pdf)

## 🔧 Current Features
- Can detect both when the mailbox is opened and the current status of mail in the box
- Uplinks a payload containing mail status and battery life to [The Things Network](https://www.thethingsnetwork.org/) via [LoRaWAN](https://www.thethingsnetwork.org/docs/lorawan/what-is-lorawan/)
- Can classify mail in light, medium and heavy categories
- Can alert user if someone opened the lid without taking or removing mail ie a Tampering Alert
- Can last up to 10 days on a single 1800mAh battery

{% include image-gallery.html images="finalProduct.jpeg, finalProduct_outside-open.jpg" height="300"%}
{% include image-gallery.html images="finalProduct_wBatteryPack.jpg, finalProduct_30deg.jpg" height="300"%}
<span style="font-size: 10px">"Images of the Final Product Installed"</span> 

{% include youtube-video.html id="1nNW60RcUi4" autoplay= "false"%}
<span style="font-size: 10px">"Video Show Case"</span>

## 📦 Requirements
- Arduino IDE
- Python (for server)

For required hardware, see this bill of materials taken from the project report:

| Item                          | Part              | Description                      | Qty | Notes                   | Total Price (€) |
| ----------------------------- | ----------------- | -------------------------------- | --- | ----------------------- | --------------- |
| **1.0 Mechanical Components** |                   |                                  |     |                         |                 |
| 1.1                           | Top Plate         | Detection Plate                  | 1   | Wood (40 × 30 × 0.5 cm) | 5.00            |
| 1.2                           | Bottom Plate      | Base for load cell               | 1   | Wood (15 × 15 × 0.5 cm) | 3.00            |
| 1.3                           | M4 Screw          | Top plate screw                  | 2   | –                       | 1.00            |
| 1.4                           | M5 Hex Nut        | Height spacer nut                | 4   | –                       | 0.50            |
| 1.5                           | M5 Screw          | Bottom plate screw               | 2   | –                       | 1.00            |
| 1.6                           | M6 Hex Nut        | Height spacer nut                | 4   | –                       | 0.50            |
| 1.7                           | Misc.             | Tape, glue                       | –   | –                       | 0.50            |
| **2.0 Electrical Components** |                   |                                  |     |                         |                 |
| 2.1                           | Load Cell + HX711 | Load cell + amplifier module     | 1   | JOY-IT                  | 6.40            |
| 2.2                           | Tilt Switch       | Ball tilt switch                 | 1   | IDUINO                  | 0.94            |
| 2.3                           | LDR               | Light-dependent resistor         | 1   | SERTRONICS              | 1.35            |
| 2.4                           | Battery           | 1800 mAh Li-Ion                  | 1   | SOLDERED                | 10.24           |
| 2.5                           | MCU + LoRa        | Xiao ESP32 + SX1262              | 1   | Seeedstudio             | 11.68           |
| 2.6                           | Antenna           | Long-range antenna               | 1   | Amphenol-SAA            | 2.69            |
| 2.7                           | 1 kΩ Resistor     | Through-hole                     | 1   | YAGEO                   | 0.10            |
| 2.8                           | 2 kΩ Resistor     | Through-hole                     | 1   | YAGEO                   | 0.10            |
| 2.9                           | Wires             | Jumper wires (various lengths)   | –   | –                       | 0.30            |
| 2.10                          | Misc.             | Breadboard, wire sleeves, solder | –   | –                       | 0.50            |
|                               |                   |                                  |     | **Tax (VAT 20%)**       | **9.16**        |
|                               |                   |                                  |     | **Grand Total (€)**     | **54.96**       |

## 🚧 Future Work
- Multi-mailbox support
- Low power design for better battery life
- Custom PCB and better housing to make the design more integrated

---
