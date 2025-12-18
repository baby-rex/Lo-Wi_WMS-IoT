# Lo-Wi WMS-IoT

## Overview

Lo-Wi WMS-IoT is a distributed water management system that combines low-power wireless communication protocols with IoT cloud integration. The system uses ESP8266 microcontrollers to create a client-server architecture for real-time water level monitoring, leveraging ESP-NOW for local mesh communication and Wi-Fi for cloud connectivity. Sensor data is transmitted to ThingSpeak for storage and visualization, with a custom Android application providing mobile access and control.

## Key Features

- Real-time water level monitoring using HC-SR04T ultrasonic sensors
- Low-latency local communication via ESP-NOW protocol
- Cloud data logging and visualization through ThingSpeak integration
- Client-server architecture for scalable sensor deployment
- Automated calibration system with visual LED feedback
- Flow rate calculation and tank volume monitoring
- Mobile application interface built with MIT App Inventor
- Portable, battery-powered client nodes for flexible installation

## System Architecture

The system implements a two-tier communication architecture. Client nodes equipped with ultrasonic sensors measure water levels and transmit data to a central server using ESP-NOW. The server aggregates this data and forwards it to ThingSpeak via Wi-Fi, enabling cloud storage and remote access through the mobile application.

![System Architecture](WMS%20BLOCK-DIAG..png)

## Tech Stack

**Hardware**
- ESP8266 microcontroller (client nodes)
- NodeMCU ESP8266 (server)
- HC-SR04T waterproof ultrasonic sensor
- LED indicators for system status
- Calibration push button

**Software & Protocols**
- Arduino IDE / C++ for embedded firmware
- ESP-NOW for peer-to-peer communication
- ThingSpeak API for cloud data storage
- MIT App Inventor for Android application development
- Wi-Fi (802.11 b/g/n) for internet connectivity

**Development Tools**
- Arduino IDE
- MIT App Inventor
- ThingSpeak platform

## How It Works

1. **Sensor Data Collection**: Client nodes measure water levels using HC-SR04T sensors at regular intervals.

2. **Local Communication**: Sensor readings are packaged and transmitted to the server via ESP-NOW protocol, providing low-latency local data exchange without internet dependency.

3. **Cloud Integration**: The server receives data from all client nodes, aggregates the information, and pushes it to ThingSpeak cloud platform over Wi-Fi.

4. **Mobile Access**: Users interact with the system through a custom Android application that retrieves data from ThingSpeak and displays real-time water levels, historical trends, and system status.

5. **Calibration**: The system includes an automated calibration mode activated via physical button press, allowing accurate flow rate measurement and tank volume calculations with visual LED feedback.

## Demo

The following video demonstrates the system in operation, showing the sensor measurement process, LED status indicators, and data transmission workflow.

https://github.com/baby-rex/Lo-Wi_WMS-IoT/assets/POC%20working.mp4

[View Demo Video](POC%20working.mp4)

## Showcase

The mobile application was developed using MIT App Inventor, providing an intuitive interface for water management monitoring and control.

![MIT App Inventor Backend](Backend%20Blocks%20of%20NeerAPI.png)

## Installation

### Hardware Setup

1. **Client Node Assembly**
   - Connect HC-SR04T sensor: Trigger to GPIO5 (D1), Echo to GPIO4 (D2)
   - Wire LED indicators: Status (D5), Calibration (D6), Constant Feed (D7), Communication (D8)
   - Connect calibration button to GPIO0 (D3) with internal pull-up
   - Power the ESP8266 via USB or external 5V power bank

2. **Server Setup**
   - Connect NodeMCU to power via USB cable
   - Ensure stable Wi-Fi network access for ThingSpeak connectivity

### Software Configuration

1. **Arduino Firmware**
   ```bash
   # Install ESP8266 board support in Arduino IDE
   # Open All_Main_Code/All_Main_Code.ino for client
   # Update server MAC address in the client code
   # Configure Wi-Fi credentials for the server
   # Upload respective sketches to client and server devices
   ```

2. **ThingSpeak Setup**
   - Create a ThingSpeak channel
   - Configure API keys in the server code
   - Set up appropriate field mappings for sensor data

3. **Mobile Application**
   - Install WMS.apk on Android device
   - Configure ThingSpeak channel ID and API credentials
   - Launch application to view real-time data

## Credits

This project was developed as a proof-of-concept for distributed IoT water management systems, integrating embedded systems, wireless protocols, and cloud platforms to create a practical monitoring solution.
