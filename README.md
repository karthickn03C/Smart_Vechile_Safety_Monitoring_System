# Smart Vehicle Safety Monitoring System

## Project Overview

The **Smart Vehicle Safety Monitoring System** is an embedded-based monitoring and safety solution developed using the PSoC 4100S Plus and ESP32 microcontrollers. The system uses CAN (Controller Area Network) communication to exchange real-time sensor information between the master and slave controllers.

The system monitors vehicle-related parameters and detects abnormal conditions to improve safety and provide timely warnings.

## System Architecture

The project follows a Master–Slave architecture.

- **Master Controller:** PSoC 4100S Plus
- **Slave Controller 1:** ESP32 – Potentiometer Monitoring
- **Slave Controller 2:** ESP32 – Ultrasonic Distance Monitoring
- **Communication Protocol:** CAN Bus
- **CAN Baud Rate:** 125 kbps

## Hardware Components

- PSoC 4100S Plus Development Board
- ESP32 Development Boards (2)
- TJA1050 CAN Transceiver Modules
- Potentiometer
- HC-SR04 Ultrasonic Sensor
- LEDs
- Connecting wires and power supply

## Working Principle

### 1. Master Controller – PSoC 4100S Plus
The PSoC acts as the main controller. It collects sensor data from the potentiometer and ultrasonic sensor and transmits the information to the ESP32 slave controllers through CAN communication.

### 2. Slave 1 – Potentiometer Monitoring
The first ESP32 receives potentiometer data using CAN ID `0x102`. It processes the received voltage value and checks the configured threshold to determine the system status.

### 3. Slave 2 – Ultrasonic Distance Monitoring
The second ESP32 receives ultrasonic distance information using CAN ID `0x101`. It calculates the distance and detects nearby obstacles based on a predefined threshold.

## CAN Communication Details

| CAN ID | Sensor | Receiver |
|---|---|---|
| 0x102 | Potentiometer | ESP32 Slave 1 |
| 0x101 | Ultrasonic Sensor | ESP32 Slave 2 |

- CAN Communication Speed: 125 kbps
- Communication Type: Standard CAN Frames

## Repository Structure

```text
Smart_Vechile_Safety_Monitoring_System/
│
├── MASTER_PSOC_4100S_PLUS
├── SLAVE_1_CODE
├── SLAVE_2_CODE
└── README.md
```

## Key Features

- Master–Slave embedded architecture
- CAN-based communication between microcontrollers
- Real-time sensor data transmission
- Potentiometer voltage monitoring
- Ultrasonic obstacle detection
- Threshold-based warning mechanism
- Modular and expandable system design

## Applications

- Automotive safety monitoring
- Obstacle detection systems
- Embedded vehicle monitoring
- CAN-based automotive applications

## Development Platform

- PSoC Creator
- Arduino IDE
- Embedded C
- ESP32
- CAN Protocol

## Project Objective

To develop a reliable embedded monitoring system using multiple microcontrollers and CAN communication for sensor data acquisition, monitoring, and safety-related warning generation.

---

**Project Domain:** Embedded Systems | Automotive Electronics | CAN Communication | IoT

**Developed as an academic engineering project.**
