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
main-image: /opAmp.webp
---

# Overview
This project focused on converting DC-driven periodic waveforms, such as square and triangle waves, into smooth sinusoidal AC signals using RC circuits and op-amps. The objective was to take basic DC signals and convert them into stable AC waveforms suitable for various applications. By using RC low-pass filters and op-amp oscillators, I was able to demonstrate how different waveforms can be shaped and generated from a single DC input source.

## Features
- **RC Low-Pass Filtering** – Converted triangle and square waves into sinusoidal signals.  
- **Waveform Shaping** – Smoothed out sharp transitions in square waves to generate more sinusoidal-like waveforms.  
- **Op-Amp Oscillator Circuit** – Generated multiple waveforms (square, triangle, and sine) simultaneously from a single circuit.  
- **Frequency Response Analysis** – Investigated how cutoff frequencies and input frequencies affect the smoothness of the output waveforms.

---
## Hardware
- **Op-Amps** – Configured as active filters and oscillators to generate and shape the waveforms.  
- **Resistors & Capacitors** – Used to build low-pass filters with adjustable cutoff frequencies to smooth out the input waveforms.  
- **Signal Generator** – Provided the initial square and triangle waveforms driven by a DC source.  
- **Oscilloscope** – Monitored and analyzed the waveform outputs to verify the conversion process.

---
## Circuit Design
### RC Low-Pass Filter  
- **Input:** 250 Hz triangle wave (2 Vpp).  
- **Output:** The triangle wave was filtered into a sinusoidal signal by adjusting the cutoff frequency (~1.2 kHz).  
- **Outcome:** A smooth sinusoidal waveform was generated from the triangle wave input, demonstrating the filtering effect.

### Square-to-Sine Conversion  
- **Input:** 250 Hz square wave.  
- **Filter Process:** The square wave was passed through a single RC filter, resulting in a partial smoothing. A second RC filter was added to further refine the output into a cleaner sine wave.  
- **Frequency Adjustments:** By tweaking the cutoff frequencies, the amplitude and smoothness of the sine wave output were optimized, highlighting the importance of filter design.

### Oscillator Circuit  
- **Objective:** The op-amp oscillator generated square, triangle, and sine waves from a single circuit.  
- **Results:** The oscillator demonstrated the ability to produce multiple waveforms simultaneously, showcasing how an active feedback network can be used to generate a variety of AC signals from a DC input.

---
## Results
- The triangle wave was effectively transformed into a sine wave after low-pass filtering.  
- The square wave required cascaded filters for smooth conversion into a clean sinusoidal output.  
- The op-amp oscillator successfully generated square, triangle, and sine waves simultaneously, demonstrating the versatility of the circuit design.  
- The filter cutoff frequencies significantly impacted the amplitude, smoothness, and overall quality of the waveforms.

---
# Summary
This project demonstrated how **RC filters and oscillator circuits** can convert DC-driven waveforms into smooth, sinusoidal AC outputs. By designing and testing low-pass filters and an op-amp oscillator, I was able to transform square and triangle waves into clean sine waves. The process highlighted the role of filter design, frequency tuning, and the use of op-amps in waveform generation.

Through this hands-on project, I gained a deeper understanding of how electronic components like resistors, capacitors, and op-amps influence waveform behavior. This experience reinforced my ability to design, analyze, and optimize circuits for practical signal conversion, laying the foundation for more advanced signal processing applications.
