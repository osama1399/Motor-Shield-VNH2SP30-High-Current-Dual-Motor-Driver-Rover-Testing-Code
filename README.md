# Motor Shield VH2SP30 High Current Dual Motor Driver/Rover Testing Code

## Introduction:

VNH2SP30 is a full bridge motor driver intended for a wide range of automotive applications. The device incorporates a dual monolithic high side driver and two low side switches. The high side driver switch is designed using the STMicroelectronic’s well known and proven proprietary VIPower M0 technology which permits efficient integration on the same die of a true Power MOSFET with an intelligent signal/protection circuitary. The VIN and motor out are pitched for 5mm screw terminals, making it easy to connect larger gauge wires. INA and INB control the direction of each motor, and the PWM pins turns the motors on or off. For the VNH2SP30, the current sense (CS) pins will output approximately 0.13 volts per amp of output current.  

## Key Features:

- Voltage Range : 5.5V - 16V 
- Maximum Current rating : 30A 
- Practical Continuous Current: 14 A 
- Current sense output proportional to motor current 
- MOSFET on-resistance: 19 mΩ (per leg) 
- Maximum PWM frequency: 20 kHz 
- Thermal Shutdown Undervoltage and Overvoltage shutdown

## Components Used:

1. Arduino Uno Board and USB
2. Monster Motor Shield VNH2SP30
3. 2 DC Motor 12V (I used Geared 775 Motors)
4. Jumper Wires / Crocodile Clip
5. Adapter / Battery (5.5V - 16V)

## Hardware Pinout

A0 : Enable pin for motor 1

A1 : Enable pin for motor 2

A2 : Current sensor for motor 1

A3 : Current sensor for motor 2

D7 : Clockwise (CW) for motor 1

D8 : Counterclockwise (CCW) for motor 1

D4 : Clockwise (CW) for motor 2

D9 : Counterclockwise (CCW) for motor 2

D5 : PWM for motor 1

D6 : PWM for motor 2

## Truthtable To Make Motor To Rotate :

Motor 0

STOP : D7 0, D8 0 & D7 1, D7 1
CCW : D7 0, D8 1
CW : D7 1, D8 0

Motor 1

STOP : D4 0, D9 0 & D4 1, D9 1
CCW : D4 0, D9 1
CW : D4 1, D9 0

## Working & Result Of This Code:

When you have finished compiling the sample source code and uploading to your arduino uno board, go to Tools > Serial Monitor and you will get a serial monitor. Set the baud rate to 9600 & and you will see the window:

![F3HFOCHIU7TQBC2](https://user-images.githubusercontent.com/75852015/141662267-6a9abd3d-61a7-4dd2-8e1f-5c27e650e9d4.png)

- When user enter number '2', dc motor start to rotate forward and serial monitor will print forward.
- When user enter '3', dc motor start to reverse and serial monitor will print reverse.
- When user enter '4', dc motor start turning right and serial monitor will print Turning Right.
- When user enter '5', dc motor start turning left and serial monitor will print Turning Left.
- When user enter '1', dc motor stop from rotating and serial monitor will print stop.
- When user enter '+', dc motor's speed increase by 10 and serial monitor will print the motor's speed. However, dc motor maximum speed is 255, thus, when user enter '++' more it will still print 255 and never more than 255 (as shown in the pic).
- When user enter '-', dc motor's speed decrease by 10 and serial monitor will print the motor's speed. However, dc motor minimum speed is 0, thus, when user enter '--' more it will still print 0 and never less than 0
