---
layout: post
title: Chess Playing Robot
description: Designing a synchronous robotic system where two people can play chess against each other remotely using robots.
github: https://robotics.hochschule-rhein-waal.de/gitlab/chess-robot/chess-playing-robot
skills: 
  - MATLAB
  - Python
  - Ardunio
  - PCB Design
  - Research
  - ROS
main-image: /Baxter.jpg
timeline: 
  - March 2024|Project Handover
  - June 2024|MagBoard Prototype
  - September 2024|LiChess interface mirroring game state from board to computer
  - November 2024|Writing the paper on MagBoard
  - May 2025|Presentation of MagBoard at ICHORA 2025
---

---
# Overview
My work as Student Research Assistant at Hochschule Rhein-Waal was to develop a human-computer chess robotic system where by a human can play chess against a computer in real life using a physical chess board with the robot acting as the medium of the computer. The concept has so far evolved to the goal of creating a system where two people can play remotely, for instance between the two campuses at Hochschule Rhein-Waal. I work under [Prof. Dr. Matthias Krauledat](https://www.hochschule-rhein-waal.de/de/user/7368) and [Prof. Dr. Ronny Hartanto](https://www.hochschule-rhein-waal.de/en/user/7875). I also worked with a fellow student assistant [Praneel Bhatia](https://www.linkedin.com/in/praneelbhatia/) who did the initial designs and prototyping of the MagBoard. 

The project is ongoing, but the primary components of the project are as follows: 

# Piece Identifiation System
## MagBoard – A Reimagined Chessboard Powered by Magnetic Proximity Sensing
To identify the class and position of the pieces, we desigend a modular 4×4 array of analogue Hall-effect sensors. Each piece is embedded with a magnet and 3D printed spacer configured to give readings within a class range. The design utilized 64 sensors, PLA 3D-printed spacers, and neodymium magnets, with theoretical modeling and validation through 180+ precision measurements using a field strength meter and digital multimeter.
- 🧲 Achieved piece position recognition with ~90% accuracy, and confirmed minimal magnetic interference (<10mT deviation) through structured interference tests.
- 🐍 Built a Python-based backend with python-chess and berserk libraries to sync board states with Li-Chess in real time, operating at 1.3Hz update frequency.
- 💡 Processed sensor data via an Arduino UNO R4 WiFi with an integrated LED matrix, running ADC at 8-bit resolution and 3.3V reference voltage.
- 📊 Proved viable classification of up to 7 piece types within a 2.5mm–10mm spacer range based on flux density variation.

{% include image-gallery.html images="heatmap_fromboard.jpg, pieces_with_magnets.jpg" height="400"%}
<span style="font-size: 10px">"Showing the basic principle"</span>  

## Presentation at ICHORA 2025
My mentoring professors, my fellow student research assistant and I presented the current design at The International Congress on Human-Computer Interaction, Optimization, and Robotic Applications (ICHORA) in Turkey in May 2025. The paper was published by [IEEE](https://ieeexplore.ieee.org/document/11016842).

For the paper, I researched and designed the experiments to investigate the magnetic flux densities at different distances. I also performed the interference tests. I wrote the sections on Design and Implementation, Results and Discussion and Conclusion. 

{% include image-gallery.html images="ichora.jpeg, ichora2.jpeg" height="400"%}
<span style="font-size: 10px">"Images from ICHORA 2025"</span>  

# Digital Chess Communication (WIP)
The board will also communicate via Python script to [Li-Chess](https://lichess.org/) where the two players will connect and essentially play against each other. The goal is to have the virtual board mirror the physical one. 
{% include image-gallery.html images="chess-diagram.png" height="400"%}
<span style="font-size: 10px">"System diagram illustrating process flow"</span>  

# Robotic Player (WIP)
Finally, the moves made on Li-Chess can be communicated to a robotic player and it will make the move in real-life. 
{% include image-gallery.html images="Baxter.jpg, ampere_robot.jpg" height="400"%}
<span style="font-size: 10px">"Some robots we have at Hochschule Rhein-Waal"</span>
  
---