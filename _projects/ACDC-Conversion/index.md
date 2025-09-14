---
layout: post
title: DC to AC Conversion with RC Circuits
description: Designed and tested RC filter and oscillator circuits to convert DC-driven periodic waveforms into sinusoidal AC signals. Implemented waveform shaping and generation using op-amps and passive components.
skills:
- Circuit Design / Breadboarding
- RC Filters
- Oscillators
- Signal Processing
- Oscilloscope Analysis
main-image: /rc_waveform.png
---

---
# Overview
This project explored how **RC circuits** and **op-amp oscillators** can be used to transform input signals and generate different waveforms. The lab focused on converting **DC-driven square and triangle waves into sinusoidal AC signals**, as well as building a circuit capable of producing **square, triangle, and sine waves simultaneously**.

## Features
- **RC Low-Pass Filtering** – Converted a triangle wave into a sinusoidal signal.  
- **Square-to-Sine Conversion** – Demonstrated waveform smoothing through cascaded filters.  
- **Op-Amp Oscillator Circuit** – Generated square, triangle, and sine wave outputs from a single circuit.  
- **Frequency Response Analysis** – Tested different cutoff frequencies and input frequencies to study waveform shaping.  

---
## Hardware
- **Op-Amps** – Configured as active filters and oscillators.  
- **Resistors & Capacitors** – Implemented low-pass filtering with tunable cutoff frequencies.  
- **Signal Generator** – Provided square and triangle input waveforms.  
- **Oscilloscope** – Captured and analyzed input/output waveforms.  

---
## Circuit Design
### Task 1 – RC Low-Pass Filter  
- Input: 250 Hz triangle wave (2 Vpp).  
- Output: Smoothed waveform approaching a sine wave.  
- Adjusted input frequency until waveform appeared most sinusoidal (~1.2 kHz).  

### Task 2 – Square Wave Input & Cascaded Filters  
- Input: 250 Hz square wave.  
- Single RC filter produced partial smoothing.  
- **Back-to-back RC filters** greatly improved sinusoidal output.  
- Varying cutoff frequency demonstrated amplitude and waveform changes.  

### Task 3 – Oscillator Circuit  
- Built op-amp oscillator with feedback network.  
- Generated **square, triangle, and sine waves simultaneously** at different circuit nodes.  
- Demonstrated waveform shaping and frequency tuning via resistors, capacitors, and potentiometer adjustment.  

{% include image-gallery.html images="rc_waveform.png" height="400" %}  

---
## Results
- Triangle wave filtered into a near-sine at ~1.2 kHz.  
- Square wave input required cascaded filters for effective sinusoidal output.  
- Cutoff frequency directly influenced amplitude and smoothness.  
- Oscillator produced three distinct waveforms (square, triangle, sine) at once, confirming proper circuit design.  

---
# Summary
This project demonstrated how **RC filters and oscillator circuits** can be used to transform basic periodic signals into sinusoidal AC waveforms. By filtering triangle and square waves, then expanding to a full oscillator design, I was able to generate sine, triangle, and square outputs from a single setup.  

The importance of this project lies in the **hands-on understanding of electronic components**. Working with resistors, capacitors, and op-amps showed how each component directly affects frequency response, waveform shaping, and overall circuit behavior. Beyond confirming theoretical knowledge, this experience proved my ability to design, adjust, and analyze circuits that perform practical signal conversions.
