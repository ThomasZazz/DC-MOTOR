# DC Motor Diagnostic System
This project is a diagnostic and measurement system for a 12V DC motor, developed using an Arduino UNO R4. It allows real-time monitoring of **voltage**, **current**, and **power**, and helps detect anomalies in motor operation based on expected no-load current values from the datasheet.

## Components Used
- Arduino UNO R4 WIFI
- 16x2 LCD display (I2C)
- Fasizi BTS7960 5.5V to 27V 43A high power motor driver module/intelligent car driver module
- Voltage sensor (DollaTek 5PCS Level 3 Sensor Module with 25V Maximum Voltage Detector for Arduino)[`/FEATURES`](./VOLTAGE SENSOR)
- Current sensor (ACS712)
- 12V DC motor(DollaTek 31ZY DC 12V 6500rpm magnetic motor tubular brushed motor with high torque)
  - DATASHEET:  
    Technical specifications:
  Voltage: 12V
  No-load current:  350mA
  Idle speed (rpm): 8000
  Nominal torque (g.cm): 200
  Rated speed (rpm): 6500
  Rated current (A):  1.6
  Stalling torque (g.cm):  1000
  Stall current (A):  6.5
- Breadboard and jumper wires
- Emergency stop button
- External 12V power supply

## Features

- Real-time monitoring of:
  - Voltage (V)
  - Current (A)
  - Power (W)
- LCD display output
- Serial monitor debug output
- Emergency stop with full system halt
- Maintenance alert logic (based on current values)
- Delayed test start and automatic stop after a fixed duration

##  How It Works

1. The system waits 20 seconds before starting the test.
2. Once started, it powers the motor and logs voltage, current, and power every 0.5 seconds.
3. If the motor's no-load current is higher than expected (based on datasheet), this suggests maintenance may be required.
4. The test ends automatically after 3 minutes or if the emergency stop is pressed.

## Code

You can find the main Arduino code inside the [`/CODE`](./CODE) folder.

