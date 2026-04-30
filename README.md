# Project Report: Industrial Anomaly Detector
**Embedded Skill Lab | Sensor & Component Interfacing**
**Team Members:** Swayam Lute, Vishakha Kadam, Bhagyashree Hinge

## 1. Project Overview & Objective
The objective of this project was to interface analog hardware components with a Raspberry Pi to create a functional Embedded System. While standard implementations often focus on basic digital I/O (e.g., turning an LED on and off), our team elected to design an **Industrial Anomaly Detector**. 

By combining a classic analog relaxation oscillator with a Python-driven edge analytics script, we simulated a "Predictive Maintenance" system. The system monitors the "heartbeat" of an analog circuit in real-time, calculates a rolling baseline average of its pulse frequency, and triggers automated warnings if the hardware’s performance degrades or drifts outside of acceptable tolerances.

## 2. Core Concept & Uniqueness (The Edge Analytics Approach)
In industrial environments, hardware degradation (such as failing capacitors or fluctuating power supplies) can lead to catastrophic system failures. 

Our project tackles this by separating the hardware and software layers:
*   **The Hardware (The Machine):** An independent analog circuit generates a continuous rhythmic pulse. 
*   **The Software (The Monitor):** The Raspberry Pi acts as an external auditing device. It does not control the pulse; it observes it. Using interrupt-driven Python logic, the Pi timestamps each pulse, calculates the time delta (interval) between flashes, and maintains a rolling average of the last 5 intervals. 
*   **The Solution:** If the analog circuit's timing drifts by more than 10% from the rolling average—simulating thermal degradation or component failure—the system instantly flags an `[ANOMALY DETECTED]` warning on a live terminal dashboard.

## 3. Hardware Architecture
Due to component availability, the initial unijunction transistor (PUT) design was upgraded to utilize the highly stable, industry-standard **NE555 Timer IC** wired in astable multivibrator mode. 

### Component List
*   **Microcontroller:** Raspberry Pi 3 Model B
*   **Timing IC:** NE555 Precision Timer
*   **Capacitor:** 100μF Electrolytic 
*   **Resistors:** 10kΩ (R1), 33kΩ (R2), 330Ω (Current Limiter)
*   **Output:** 5mm Red LED

### Circuit Integration
The 555 Timer is powered directly from the Raspberry Pi's 5V and Ground pins, eliminating the need for external batteries. The resistor-capacitor (RC) network dictates the charge/discharge cycle, creating a steady flash at the output (Pin 3). A single jumper wire interfaces the positive leg of the LED to **GPIO 17 (Physical Pin 11)** on the Raspberry Pi, safely transmitting the 5V logic HIGH signal to the Pi without risking current overload.

## 4. Software Implementation
The software was written in Python, utilizing the `RPi.GPIO` library. Instead of using a resource-heavy `while` loop to constantly check the pin state, the code utilizes **Hardware Interrupts** (`GPIO.add_event_detect`). 

This means the Python script runs asynchronously; the instant the GPIO pin detects a rising edge (the LED turning on), it triggers a callback function to record the exact system time. This approach ensures microsecond accuracy for our data analytics dashboard and demonstrates efficient use of microcontroller processing power.

## 5. Division of Labor
To ensure a comprehensive understanding of the system, the project development was divided into three distinct engineering roles:



## 6. Conclusion
This project successfully demonstrates the integration of fundamental analog circuitry with modern, data-driven software architecture. By moving beyond simple sensor reading and implementing real-time data analysis, we successfully built a robust, context-aware Embedded System capable of identifying its own hardware faults. This framework serves as a foundational model for advanced IoT diagnostics and edge computing applications.

---

# Industrial Anomaly Detector (GitHub README)
**Repository:** `SkillLab2_Embedded_P-O`

## Overview
This project bridges the gap between fundamental analog hardware and modern edge computing. Built for the Embedded Systems Skill Lab, the **Industrial Anomaly Detector** simulates a predictive maintenance pipeline used in factory environments to monitor the health of motors, pumps, and oscillating hardware.

Instead of relying on standard digital I/O tasks, this system isolates the hardware and software layers:
1. **The Hardware:** An independent analog relaxation oscillator (using an NE555 Precision Timer) generates a continuous, rhythmic "heartbeat" pulse.
2. **The Software:** A Raspberry Pi acts as an external auditing device. It passively monitors the pulse using hardware interrupts, calculates real-time performance metrics, and triggers alerts if the hardware timing drifts outside safe tolerances.

## Features
* **Analog Rhythmic Oscillation:** Pure hardware-driven pulse generation independent of the microcontroller's CPU.
* **Asynchronous Edge Detection:** Uses Python `RPi.GPIO` hardware interrupts to track voltage spikes with microsecond precision, preventing CPU bottlenecking.
* **Real-Time Data Analytics:** Calculates a continuous rolling average of the hardware's pulse interval.
* **Automated Anomaly Detection:** Flags any pulse that drifts more than 10% from the established baseline, simulating the detection of thermal degradation or component failure.
* **Live Terminal Dashboard:** Provides a rich, text-based UI displaying total pulses, session uptime, live interval times, and a system stability rating.

## Hardware Architecture

### Components
* Raspberry Pi 3 Model B
* NE555 Precision Timer IC
* 100μF Electrolytic Capacitor
* 5mm Red LED
* Resistors: 10kΩ, 33kΩ, 330Ω
* Solderless Breadboard & Jumper Wires

### Wiring & Pinouts
The 555 Timer is wired in astable multivibrator mode, powered directly from the Raspberry Pi.

| Raspberry Pi Pin | Connection | Description |
| :--- | :--- | :--- |
| **Pin 2 (5V)** | Breadboard Power Rail (+) | Powers the 555 Timer circuit. |
| **Pin 6 (GND)** | Breadboard Ground Rail (-) | Establishes a common ground. |
| **Pin 11 (GPIO 17)** | LED Positive Leg (Anode) | The data monitoring wire. Reads the voltage spike when the timer fires. |

**NE555 Astable Configuration:**
* **Pin 1 (GND):** Ground
* **Pin 8 (VCC) & Pin 4 (Reset):** 5V Power
* **Pin 2 (Trig) & Pin 6 (Thresh):** Tied together, connected to the 100μF Capacitor positive leg.
* **Pin 7 (Discharge):** Connected between the 10kΩ and 33kΩ timing resistors.
* **Pin 3 (Output):** Connected to the 330Ω resistor and the LED.

## Software Setup & Execution

### Prerequisites
The system runs on Python 3 and requires the standard Raspberry Pi GPIO library.
```bash
pip3 install RPi.GPIO
