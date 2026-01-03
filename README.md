# peltier-educational-kit
This repository presents an educational device kit for control education. The kit is composed of simple and low-cost components, making it easy to replicate. It allows students to implement and experimentally validate control algorithms.

The main idea of the device is to provide a small-scale thermal control system consisting of temperature sensors, a Peltier cell as the actuator, and interface circuits. 
It serves as a practical platform for studying temperature regulation, testing control strategies, and observing the effects of disturbances in a controlled environment.



## Overview
The kit consists of two main components: the interface circuit and the Peltier cell (process). The image below shows the operating principle of the kit:

<img src="images/block%20diagram2.jpg" alt="Kit principle" width="500">

The computer hosts the controller implemented in MATLAB/Simulink. Communication with the hardware interface is achieved via Bluetooth serial communication, which manages the sensors and actuators.


The Peltier cell is housed in a 3D-printed case. Inside the case, in addition to the cell, there are two fans, a power resistor, and two temperature sensors (one digital and one analog).

One of the two fans, aided by a heat sink, is used to keep the uncontrolled side of the cell cool. This fan is always on. The other fan can be conveniently used to apply a load disturbance on the controlled side of the cell. The power resistor introduces another source of disturbance on the load but it creates the opposite effect (the fan removes heat, while the resistor generates heat).

To improve heat conduction between the cell, the sensors, and the resistor, a thin metal plate has been inserted.

The digital temperature sensor used is the DS18B20, a digital sensor that communicates via the 1-Wire protocol. It offers high accuracy. This sensor has virtually no measurement noise.

In order to have some measurement noise and therefore to test the capability of a controller to handle this issue, we have introduced another analog temperature sensor, namely, the LM35 sensor, by intentionally omitting the filter capacitor. This allows the user to decide which sensor to use, with noise or without noise, so that he/she can face the problem of measurement noise in designing the control strategy, dealing with a typical issue in industrial environments.



The image below shows the exploded 3D assembly in which all the components can be seen:

<img src="images/3D exploded.jpg" alt="3D exploded" width="500">

<ol>
  <li> Support </li>
  <li> Fan </li>
  <li> Power resistor </li>
  <li> Peltier cell </li>
  <li> Internal support </li>
  <li> Temperature sensors </li>
  <li> Heat-sink </li>
  <li> Housing </li>
</ol>

## Interface circuit

The purpose of the circuit is to interface sensors and actuators with a personal computer through serial wireless communication based on Bluetooth connectivity. We have chosen to use wireless communication between the PC and the circuit in order to protect the PC in case of a circuit failure, such as a short circuit. In addition, wireless communication is more user-friendly as it allows the user to achieve the same performance of a wired connection with more flexibility. The circuit is powered by 12V DC supply obtained from a standard power adapter. The working principle of the interface circuit, which is managed by an Arduino Nano, is shown in Figure below:

<img src="images/block diagram1.jpg" alt="interface circuit working principle" width="500">

The digital logic signals are shown in blue, power signals in red, and analog signals in green.

A simple serial communication protocol is implemented in the firmware, allowing data exchange between the control software and the process by sending properly formatted strings. This enables actuator control and sensor data acquisition. Thanks to this approach, the interface circuit can be used with any software capable of serial communication, such as Java, Python, or Matlab/Simulink.

In the case of Matlab/Simulink, no additional libraries are required, since native serial communication commands are used. To further simplify usage, the protocol is encapsulated in dedicated Matlab functions. The user only needs to import these functions into the workspace and call them when data exchange is required, without needing to know the underlying communication protocol.

The interface circuit is managed by an Arduino Nano, which receives serial commands and controls the actuators. The Peltier cell is driven by a high-frequency PWM-modulated voltage through a MOSFET. To enable both heating and cooling on the same side of the cell, a relay-based H-bridge is implemented to invert the applied voltage. An additional MOSFET and a BJT are used to control a power resistor and a cooling fan. The power resistor can be PWM-controlled to generate load disturbances for experimental testing.

Temperature feedback is provided by both a digital and an analog sensor. The digital sensor is read on request and its value is sent back to the software via serial communication. The analog sensor is read through an analog input, and the firmware converts the measured voltage directly into temperature in degrees Celsius, relieving the user from handling this conversion.

Bluetooth serial communication is implemented using an HC-05 module connected in parallel to the Arduino RX and TX pins. To allow firmware reprogramming, the module can be temporarily disconnected using a dedicated button, which must be pressed during firmware upload via the Arduino IDE.



The circuit board is shown in figure below:

<img src="images/Interface circuit.jpg" alt="interface circuit" width="500">

<ol>
  <li> 12V DC Connector </li>
  <li> Arduino Nano board </li>
  <li> Programming button </li>
  <li> Bluetooth HC-05 module </li>
  <li> Wiring to the cell </li>
</ol>

## Educational Objectives

## Repository Structure

The repository is organized as follows:

- `docs/` → Documentation, assembly instructions, and experiments (coming soon...)
- `images/` → Images and figures
- `hardware/` → Schematics and PCB files 
- `firmware/` → Microcontroller firmware (coming soon...) 
- `software/` → MATLAB scripts and functions (coming soon...) 
- `LICENSE` → Licensing information

## License

This project is released under the  
**Creative Commons Attribution–NonCommercial–ShareAlike 4.0 International License (CC BY-NC-SA 4.0)**.

Use of this project is permitted exclusively for educational, study, and research purposes.  
Any commercial use is strictly prohibited without explicit authorization from the author.

Full license text: [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

