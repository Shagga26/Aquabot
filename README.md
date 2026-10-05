# AQUABOT: Autonomous Water & Pollution Sentinel

Aquabot is a 4-wheel drive (4WD) agricultural patrol rover designed to monitor feeder canals and open irrigation channels in real time. It solves the operational inefficiency of manual environmental sampling by replacing intermittent human patrols with continuous automated telemetry.

## 🧠 System Architecture
The robot operates on a dual-microcontroller system to separate locomotion from data processing:
*   **Locomotion & Control (Arduino Uno):** Drives the 4WD chassis and receives manual steering inputs via a PS2 Wireless Controller.
*   **Autonomous Navigation:** Utilizes a 5-channel infrared (IR) line-tracking array to autonomously follow perimeter reference tracks using an Active-LOW logic system.
*   **Telemetry Hub (ESP32):** Reads analog inputs from a capacitive soil moisture sensor and a glass pH sensor probe held in continuous contact with the canal flow. 
*   **Alerts & IoT:** Streams live pH and moisture percentages to a Blynk IoT cloud dashboard over Wi-Fi, while triggering an onboard Red/Yellow/Green LED array and active buzzer if pollution is detected.

## ⚙️ Hardware Stack
*   **Microcontrollers:** Arduino Uno R3, ESP32 Wi-Fi Module.
*   **Chassis:** 4WD Rover Chassis (Nexha Bot).
*   **Sensors:** 5-Channel Line Tracking Sensor Array, Capacitive Soil Moisture Sensor, Analog pH Sensor Module.
*   **Visuals & Alerts:** 16x2 I2C LCD Display, Red/Yellow/Green Status LEDs, Active Buzzer.
*   **Control:** PS2 Wireless Controller (2.4 GHz).

## 🚀 Core Features
1.  **Autonomous Line Tracking:** Employs a 5-sensor array with programmed soft-turns and hard-turns to smoothly follow complex canal paths.
2.  **Continuous Environmental Sensing:** Constantly tests the water to read exact soil moisture percentages and pH levels.
3.  **Smart Alert Logic:** If the moisture level indicates a dry canal, or if the pH falls outside the safe baseline (6.0–8.5), the system triggers local hardware alarms and pushes a real-time warning to the Blynk app.

## 🌍 SDG Alignment
Designed for the WSDG 2026 International STEM Challenge (Primary Category), Aquabot directly addresses **SDG 6 (Clean Water and Sanitation)** and **SDG 2 (Zero Hunger)** by preventing toxic agricultural runoff from destroying harvests and maintaining sustainable irrigation practices.
