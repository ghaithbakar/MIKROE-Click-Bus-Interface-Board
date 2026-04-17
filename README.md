# MIKROE Click Bus Interface Board — VCNL4035X01 Proximity Sensor

A sensor interface PCB built around the **VCNL4035X01 proximity and gesture 
detection IC**, designed to plug into any MIKROE MikroBUS host connector. 
Designed as part of EEE394 (Printed Circuit Design Fundamentals) at 
Arizona State University.

## Overview

This board is more than a simple adapter — it integrates a **Vishay 
VCNL4035X01** proximity/gesture sensor IC with **three VSMY2850RG IR 
emitter LEDs** and exposes the sensor data to a host microcontroller via 
**I2C over the standard MIKROE MikroBUS connector**. An interrupt line (INT) 
notifies the host when proximity or gesture events are detected, without 
requiring continuous polling.

## Schematic Highlights

| Block | Components |
|---|---|
| Proximity/Gesture IC | VCNL4035X01-GS08 |
| IR Emitters | 3× VSMY2850RG IR LEDs |
| Status LED | AP1608SGC green LED + 470Ω resistor |
| I2C Pull-ups | 3× 4.7KΩ resistors (SDA, SCL, INT) |
| Decoupling | 3× 100nF, 1× 22µF, 1× 10µF |
| Host Interface | MIKROE MikroBUS connector (I2C: SDA/SCL + INT) |
| Power Input | P1 header — 5V, VCC, VCC_3V3 |
| Supply Voltage | 3.3V logic / 5V available |
| PCB Layers | 2 |

## How It Works

The VCNL4035X01 drives three IR LEDs (IRED1–IRED3) to emit infrared pulses 
and measures reflected IR intensity to detect proximity and directional 
gesture inputs. The sensor communicates with the host via I2C (SDA/SCL), 
with 4.7KΩ pull-up resistors on both lines plus the interrupt line. When a 
proximity or gesture threshold is crossed, the INT pin pulls low to signal 
the host MCU. The MikroBUS connector exposes I2C, INT, power (3.3V/5V), 
and ground — making it compatible with any MikroBUS host board including 
the companion MCU board in this repo series.

## Status
✅ Designed · ✅ Manufactured · ✅ Assembled · ⚠️ IR emitter placement non-conformant 
— emitters placed on surface rather than through-hole per spec · ⏳ System test pending
## Tools Used

Altium Designer · Soldering Station

## Key Skills Demonstrated

Sensor IC integration · I2C bus design with pull-up network · 
Interrupt-driven hardware signaling · MIKROE MikroBUS ecosystem compatibility · 
Multi-rail power distribution (3.3V/5V) · Decoupling network design · 
Gerber/BOM/NC drill generation
