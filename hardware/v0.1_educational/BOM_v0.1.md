## Bill of Materials – Version v0.1

These components are intended for the PCB assembly:

| PCB reference      | Component            | Value / Part Number    | Qty | Notes                                     |
|-------:            |----------------------|------------------------|-----|-------------------------------------------|
| R1 R4              | Resistor             | 10 Ω 1/4W              | 2   | MOS gate resistor                         |
| R2 R3 R6 R7 R8     | Resistor             | 470 Ω 1/4W             | 5   | LED and BJT base resistor                 |
| R5                 | Resistor             | 4.7 kΩ 1/4W            | 1   | Pull-up resistor                          |
| Q1 Q3              | NPN Transistor       | BC547                  | 2   | Relè and FAN driver                       |
| Q2 Q4              | N-MOSFET             | IRFZ44N                | 2   | Peltier and resistor driver               |
| D1                 | Diode                | 1N4007                 | 1   | Flyback diode                             |
| LED1 LED2 LED3     | Led diode            | Led 5mm                | 3   | Indicator leds                            |
| C1 C2              | REMOVED              | REMOVED                | 0   | REMOVED                                   |
| C3                 | Capacitor            | 4.7uF 50V              | 1   | Voltage stabilizer                        |
| K1                 | Relay                | RTE24012               | 1   | H-Bridge for Heating/Cooling inversion    |
| U1                 | Microcontroller      | ATmega328P             | 1   | Arduino Nano                              |
| U3                 | Button               | 5.8 × 5.8 mm DIP 6-pin | 1   | Button for USB programming                |
| U4                 | Voltage Regulator    | LM7805                 | 1   | 5V regulator                              |
| HC-05              | Bluetooth module     | HC-05                  | 1   | Bluetooth module for serial connection    |
| Connector          | Connector            | KF301-5.0-3P           | 2   | Connector for LM35 and DS18B20 wiring     |
| Connector          | Connector            | KF301-5.0-2P           | 5   | Connector for other wiring                |


These components are required to build the Peltier educational kit and are mounted inside the 3D-printed case.

| Component            | Value / Part Number    | Qty | Notes                                     |
|----------------------|------------------------|-----|-------------------------------------------|
| Peltier cell         | TEC1-12705             | 1   | Actuator                                  |
| Temperature sensor   | LM35                   | 1   | Analog sensor                             |
| Temperature sensor   | DS18B20                | 1   | Digital sensor                            |
| FAN                  | DC 5010                | 2   | Cooling and disturbance FANs 50x50x10mm   |
| Heatsink             | 40x40x11mm             | 1   | Cooling heatsink                          |
| Power resistor       | 10 Ω 5W                | 1   | Disturbance resistor                      |



