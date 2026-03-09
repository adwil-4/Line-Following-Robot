# Line Following Robot 🤖

> Autonomous line-following robot using infrared sensors and a Raspberry Pi Pico.

## Overview

An autonomous line-following robot built using a **Raspberry Pi Pico** and **infrared (IR) sensors**. The robot detects and follows a black line on a white surface using a PID control system for smooth and accurate tracking. This project provided foundational experience in sensor integration, real-time control systems, and autonomous robot design.

## Features

- 📏 **Line Detection** — IR sensors detect line position relative to robot centre
- 🎛️ **PID Control** — Proportional-Integral-Derivative controller for smooth tracking
- ⚡ **Real-Time Response** — Continuous sensor polling and immediate motor adjustments
- 🔄 **Intersection Handling** — Detects and navigates T-junctions and crossings
- 🏁 **End Detection** — Stops at the end of the line path

## Control System

```
IR Sensor Array (5 sensors)
    ↓
Line Position Calculation (Weighted average)
    ↓
Error = Target Position - Current Position
    ↓
PID Controller → Motor Speed Correction
    ↓
Left Motor Speed / Right Motor Speed
    ↓
Line Following Behaviour
```

## PID Tuning

| Parameter | Value |
|---|---|
| Kp (Proportional) | Tuned per surface |
| Ki (Integral) | Low (prevents drift) |
| Kd (Derivative) | High (smooth response) |

## Tech Stack

| Category | Tools |
|---|---|
| Microcontroller | Raspberry Pi Pico |
| Language | MicroPython |
| Sensors | IR Sensor Array (TCRT5000) |
| Actuation | DC Motors + L298N |
| Control | PID Controller |

## Project Structure

```
Line-Following-Robot/
├── main.py            # Main control loop
├── ir_sensors.py      # IR sensor array driver
├── motors.py          # Motor control
├── pid.py             # PID controller implementation
├── config.py          # Tuning parameters
└── README.md
```

## Getting Started

### Hardware Required

- Raspberry Pi Pico
- 5× IR Sensors (TCRT5000)
- L298N Motor Driver
- 2× DC Gear Motors
- Robot chassis + wheels
- 5V battery pack

### Setup

1. Flash MicroPython onto the Pico
2. Wire IR sensors to GPIO pins per `config.py`
3. Upload all files using Thonny or `mpremote`
4. Run `main.py`

## Results

- ✅ Reliable line following on standard black-on-white tracks
- ✅ Smooth cornering using PID control
- ✅ Handles T-junctions and curved paths

## Skills Demonstrated

`Raspberry Pi Pico` · `MicroPython` · `PID Control` · `IR Sensors` · `Line Following` · `Autonomous Robotics` · `Embedded Systems`
