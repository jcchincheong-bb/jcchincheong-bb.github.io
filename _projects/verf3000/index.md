---
layout: post
title: The Verificatinator 3000
description: Design for a mobile force verification unit (only concept, no implementation).
github: https://github.com/jcchincheong-bb/Verificationator_GP-WS25-26
skills: 
  - PCB Design
  - Circuit Design
  - Group Work
  - Signal Conditioning
  - Cost Estimation
  - Production Planning
main-image: /case.png
timeline:
  - October 2025|Product Concept
  - December 2025|Product Design - 3D Model, Circuit
  - January 2026|Documentation and Report
---

---
# Overview
This project was done as part of the Group Project Module at HSRW in WS25/26. It was done under requirements provided by [Innovatest](https://www.innovatest-europe.com/). The full report can be found [here](https://github.com/jcchincheong-bb/Verificationator_GP-WS25-26/blob/main/Group%2002_WS_25-26%20Milestone%203.pdf).

# Abstract
The Verificationator project is focused on the design of a highly portable, robust, and user-friendly solution that allows technicians to verify and calibrate hardness testers directly in the field. The project’s scope spans from the concept design to the project documentation and the design of an interactive brochure. The project spanned from October 5th, 2025, to January 13th, 2026. Five engineering students make up the interdisciplinary design team, and the project was completed under the guidance of Hochschule Rhein-Waal professors and scientific staff.

Initial market analysis revealed that the market for hardness testers is growing and ready for such a portable verification kit. The initial concept proposed a fully integrated system which can operate safely in factory environments, has an ergonomic HMI, and can automatically identify and operate with Innovatest load cell models ranging from 10 gf to 3,000 kgf. The production budget was set to €4,000 per unit, ensuring competitiveness on the market.

From a mechanical standpoint, the device uses an IP-67 rated rugged pelican case with an aluminium chassis mounted inside to house the electronics. Medium density foam inserts surround this chassis to provide shock absorption and padding. Load cells are stored in dedicated foam compartments on the opposite side of the case, allowing secure transport without damage or misalignment. A complete 3D model was constructed to demonstrate all mechanical connections, fasteners, sealants, and other features to create a device that is suited for harsh factory environments. To document the entire mechanical design, a technical assembly drawing was done according to DIN 406.

On the electrical side of the design, a complete schematic diagram and preliminary PCB were designed to match all functionality requirements with the utmost precision and speed. An advanced measurement chain was designed to process the load cell signals and gives a noise-free resolution of 17 bits, classifying as a Class A measuring device by OIML. The design also incorporates high-performance components such as the ESP32-P4, allowing for incredible signal processing and input responsiveness. The control, power management, and battery management circuits were designed to give a battery life of 9.16 hours and advanced features such as switching between 5 V and 10 V excitation and real-time graphing. The complete program logic of the microcontroller is documented in a programming flow chart to illustrate the main settings, interrupts, and other processes.

After a Make or Buy analysis was performed, the pelican case and electrical components were specified in the requirements manual, and the custom-made aluminium and foam interior manufacturing techniques were defined. A complete BOM was then done after careful selection of components. After which, the complete production and assembly plan was defined, revealing a takt time of 756 min/unit and a total production time of 1032 min/unit, suggesting parallel manufacturing or outsourcing may be required. The assembly time, on the other hand, was found to be only 142 min/unit.

Finally, the costs of all the materials, labour, manufacturing, and overheads were considered to calculate a production cost of €3990.15. Accounting for business overheads, profit, and commission, the final offer price was found to be €7018.28.

{% include youtube-video.html id="Xx_LVumxhoE" autoplay= "false"%}
<span style="font-size: 10px">"Video Show Case"</span>

# Development Team
- [Abhinav Kothari](https://www.linkedin.com/in/abhinav-kothari-2ak/) - Manufacturing and Production Planning, Video Editing
- Ahmad Zeaiter - Mechanical Design, Technical Drawing, Brochure Design
- [Justin Julius Chin Cheong](https://jcchincheong-bb.github.io/) - Project Management, Market Analysis, Cost Estimation, System Architecture and Signal Conditioning Design
- Wasim Ahmed Mohammed Al Asbahi - Main Electrical Design, Programming Flowchart

---
