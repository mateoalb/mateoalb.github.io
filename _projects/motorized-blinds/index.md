---
layout: post
title: Motorized Blinds
description:  Designed and built a smart blind system using an ESP32 and motor driver. Integrated 3D-printed components for mounting, enabling remote and automated control of window blinds
skills: 
- 3D Printing / Desgining
- Arduino / Esp32
- Breadboarding
- Basic Circuit Desgin
- C++
main-image: /IMG_1889.jpeg
---

---
# Overview
This project showcases my custom built motorized blind, designed to integrate seamlessly with Apple HomeKit using homespan. I developed two versions, one powered by a servo motor and another using a DC motor with a driver board in order to explore different approaches for torque, reliability, and installation flexibility.

## Features
- HomeKit Integration – Built with HomeSpan, an open-source library that brings native HomeKit support to ESP32 boards.
- Two Motor Options:
  - Servo Motor Version
  - DC Motor Version
- 3D-Printed Connector – Custom-designed attachment connects the motor shaft to the blinds’ tilt rod.
- [Homekit](https://github.com/HomeSpan/HomeSpan/tree/master) Control – Operated directly from an apple device.

## Hardware
- Esp32 - needed for homespan
- DC Motor + Driver Board / Servo
- Breadbaord
- Power
    - 12V DC power suply - needed depnding on motor used
    - USB-C breakout - optioinal makes easy power delivery
    - On Board
 
---
## 3D Printed
- To bridge the gap between the motors and the blinds’ tilt rod, I designed a custom 3D-printed connector. This part ensures a secure, reliable fit while remaining easy to remove or swap. The connector was ajdusted for each type
{% include image-gallery.html images="mount3Dfile.png" height="400" %} 
  
