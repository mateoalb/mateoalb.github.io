---
layout: post
title: Traffic Light Controller
description: Designed and implemented a traffic light controller on the Zybo Z7-10 FPGA board using behavioral Verilog and FSM design. The controller manages a highway–farm road intersection with timed light cycles and sensor-based responsiveness.
skills:
- Verilog / HDL
- FSM Design
- FPGA Programming
- Digital Logic Simulation
- Zybo Z7-10
main-image: /tLight.jpg
---

---
# Overview
This project demonstrates the design and implementation of a **traffic light controller** for a highway farm road intersection. Built on the Zybo Z7-10 FPGA board, the system ensures safe traffic flow by cycling through green, yellow, and red lights with appropriate timing. The design uses a Mealy FSM written in behavioral Verilog and integrates a sensor to dynamically adjust light changes depending on traffic conditions.

## Features
- **FSM-Based Control** – Implemented using a Mealy finite state machine for precise sequencing.  
- **Timed Light Transitions** – Integrated counters enforce realistic green/yellow/red durations.  
- **Sensor Integration** – Farm road sensor prioritizes highway traffic unless vehicles are detected on the farm road.  
- **FPGA Implementation** – Designed, simulated, and tested on the Zybo Z7-10 development board.  

---
## Hardware
- **Zybo Z7-10 FPGA Board** – Used to program and test the traffic light controller.  
- **Pushbutton Input** – Configured as a farm road traffic sensor.  
- **LED Outputs** – Represented highway and farm road signals.  
- **Vivado XDC File** – Used to map signals to physical FPGA pins.  

---
## FSM Design
- Two outputs (`highwaySignal`, `farmSignal`) represent traffic lights:  
  - `11` → Green  
  - `10` → Yellow  
  - `01` → Red  
- Base controller cycles highway and farm lights in timed intervals.  
- Modified FSM checks the **farm sensor**:  
  - In highway green state, if the sensor is high (and ≥30 seconds elapsed), it switches to yellow.  
  - In farm green state, if the sensor goes low, it transitions back to yellow.  

{% include image-gallery.html images="fsm.png" height="400" %}  

---
