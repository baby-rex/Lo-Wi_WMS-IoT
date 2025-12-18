# Lo-Wi WMS-IoT

## Overview

Lo-Wi WMS-IoT is a Water Management System designed for real-time monitoring and data collection using IoT-enabled microcontrollers. The system employs ESP8266 and NodeMCU devices to measure water levels via ultrasonic sensors, transmit data wirelessly using ESP-NOW protocol, and push readings to cloud platforms for visualization and analysis. The solution includes a custom Android application built with MIT App Inventor for remote monitoring and control.

## Key Features

- Real-time water level monitoring using HC-SR04T ultrasonic sensors
- Wireless data transmission via ESP-NOW protocol between client and server nodes
- Cloud integration with ThingSpeak for data storage and visualization
- Custom Android application for mobile monitoring and control
- Calibration system with visual LED indicators for system status
- Low-power ESP8266-based hardware for field deployment
- Wi-Fi connectivity for remote data access

## System Architecture

The system follows a client-server architecture where ESP8266 microcontrollers act as clients that collect sensor data and transmit it to a NodeMCU server. The server aggregates data and forwards it to ThingSpeak cloud platform via Wi-Fi. The architecture enables scalable deployment with multiple sensor nodes reporting to a central server.

![System Architecture](WMS%20BLOCK-DIAG..png)

## Tech Stack

**Hardware:**
- ESP8266 microcontrollers
- NodeMCU (ESP8266-based)
- HC-SR04T ultrasonic sensors
- LED indicators for system status
- Breadboard power supply modules

**Software:**
- Arduino IDE
- ESP8266 Arduino Core
- ESP-NOW protocol library
- NewPing library for ultrasonic sensors
- MIT App Inventor for Android application development

**Cloud Services:**
- ThingSpeak IoT platform

## How It Works

1. **Client Nodes**: ESP8266 clients continuously measure water levels using ultrasonic sensors and calculate flow rates during calibration periods
2. **Data Transmission**: Measured data is transmitted wirelessly to the NodeMCU server using the ESP-NOW protocol
3. **Server Processing**: NodeMCU receives data from multiple clients and maintains Wi-Fi connectivity for cloud communication
4. **Cloud Upload**: Server forwards sensor readings to ThingSpeak for persistent storage and real-time visualization
5. **Mobile Access**: Android application retrieves data from ThingSpeak API, enabling remote monitoring and control

LED indicators on client nodes provide visual feedback for calibration status, data transmission, and system health.

## Demo

The following video demonstrates the proof of concept implementation, showing the hardware setup, sensor calibration process, and real-time data transmission:

[Watch Demo Video](POC%20working.mp4)

<video src="POC%20working.mp4" controls></video>

> Note: If the video does not play inline, click the link above to download and view it.

## Showcase

The Android application was developed using MIT App Inventor, providing an intuitive interface for water management monitoring. The block-based programming approach enabled rapid prototyping and deployment.

![MIT App Inventor Implementation](Backend%20Blocks%20of%20NeerAPI.png)

## Installation

### Hardware Setup

1. Connect HC-SR04T ultrasonic sensor to ESP8266:
   - Trigger pin to GPIO5 (D1)
   - Echo pin to GPIO4 (D2)
   - VCC to 5V, GND to GND

2. Connect LED indicators:
   - Status LED to GPIO14 (D5)
   - Calibration LED to GPIO12 (D6)
   - Constant speed LED to GPIO13 (D7)
   - Communication LED to GPIO15 (D8)

3. Connect calibration button to GPIO0 (D3)

### Software Setup

1. Install Arduino IDE and ESP8266 board support
2. Install required libraries:
   - ESP8266WiFi
   - ESP-NOW
   - NewPing

3. Configure Wi-Fi credentials in server code
4. Update MAC address in client code to match your NodeMCU
5. Upload client code to ESP8266 nodes
6. Upload server code to NodeMCU
7. Install WMS.apk on Android device

### Running the System

1. Power up all ESP8266 client nodes
2. Power up NodeMCU server
3. Press calibration button to establish baseline measurements
4. Monitor LED indicators for system status
5. Access data via ThingSpeak dashboard or mobile application

## Credits

This project was developed as a proof of concept for IoT-based water management systems. The implementation leverages open-source libraries from the ESP8266 community and utilizes MIT App Inventor for mobile application development.

Documentation and technical specifications are provided in Doc.md and Module.pdf for detailed reference.
