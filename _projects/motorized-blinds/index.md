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

---
## Code
- Servo Code - adjusted the windowshade example code in Homespan library to fit
  ```cpp
    #include "HomeSpan.h"
    #include <Servo.h>
  
    struct DEV_WindowShade : Service::WindowCovering {
      Characteristic::CurrentPosition currentPos{0,true};
      Characteristic::TargetPosition targetPos{0,true};
      Servo servo;
      int servoPin;
    
      DEV_WindowShade(int pin) : Service::WindowCovering() {
        servoPin = pin;
        servo.attach(servoPin);
    
        LOG0("Initial Shade Position: %d\n", currentPos.getVal());
        // Move servo to initial position
        int angle = map(currentPos.getVal(), 0, 100, 0, 180);
        servo.write(angle);
      }
      boolean update() {
    
        if (targetPos.updated()) {
          int angle = map(targetPos.getNewVal(), 0, 100, 0, 180);   // scale HomeKit
          servo.write(angle);
    
          LOG1("Setting Shade Position=%d (Servo Angle=%d)\n", targetPos.getNewVal(), angle);
    
          // Update current position immediately (servo moves directly)
          currentPos.setVal(targetPos.getNewVal());
        }
    
        return (true);
      }
    
      void loop() {
        // Nothing needed here since servo moves immediately
      }
    };
    
    void setup() {
      Serial.begin(115200);
    
      homeSpan.begin(Category::WindowCoverings, "Servo Shade");
    
      new SpanAccessory();
        new Service::AccessoryInformation();
          new Characteristic::Identify();
        new DEV_WindowShade(23);   // attach servo to GPIO 23 (change if needed)
    }
    void loop() {
      homeSpan.poll();
    }
  ```
  
- DC Motor Code - adjusted the windowshade example code in Homespan library to fit
  ```cpp
   #include "HomeSpan.h"
  
    struct DEV_WindowShade : Service::WindowCovering {
    
      Characteristic::CurrentPosition currentPos{0,true};
      Characteristic::TargetPosition targetPos{0,true};
      
      StepperControl *mainMotor;   // motor to open/close shade
    
      DEV_WindowShade(StepperControl *mainMotor) : Service::WindowCovering(){
    
        this->mainMotor=mainMotor;                         
               
        mainMotor->setAccel(10,20);                         // set acceleration parameters
        mainMotor->setStepType(StepperControl::HALF_STEP);  // set step type
    
        LOG0("Initial Open/Close Position: %d\n",currentPos.getVal());
        
        mainMotor->setPosition(currentPos.getVal()*20);     // define initial position
      }
      boolean update(){
        if(targetPos.updated()){
          // Move motor to absolute position
          // Assuming 400 steps/rev and 5 revs for full open/close = 2000 steps
          // Multiply targetPos (0-100) by 20
          mainMotor->moveTo(targetPos.getNewVal()*20,5,StepperControl::BRAKE);
          LOG1("Setting Shade Position=%d\n",targetPos.getNewVal());
        }
    
        return(true);
      }
    
      void loop(){
    
        // Update Current Position when motor stops
        if(currentPos.getVal()!=targetPos.getVal() && !mainMotor->stepsRemaining()){
          currentPos.setVal(targetPos.getVal());
          LOG1("Main Motor Stopped at Shade Position=%d\n",currentPos.getVal());
        }           
      }
      
    };
    void setup() {
    
      Serial.begin(115200);
    
      homeSpan.begin(Category::WindowCoverings,"Motorized Shade");
    
      new SpanAccessory();                                                          
        new Service::AccessoryInformation();
          new Characteristic::Identify(); 
        // Instantiate single stepper driver (example uses TB6612)
        new DEV_WindowShade(new Stepper_TB6612(23,32,22,14,33,27));
    }
    
    void loop(){
      
      homeSpan.poll();  
    }

  ```
  ---
# Summary
- This project successfully combined hardware, software, and custom 3D-printed parts to create a functional and reliable smart blind system. It demonstrates my ability to integrate electronics with mechanical design for practical home automation solutions.
