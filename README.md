# Smart Soil Monitoring and Irrigation System

## Project Overview
This project is a **smart soil monitoring system** that collects real-time data on **temperature, moisture, and soil nutrients (NPK)**. The data is processed by an **ATtiny85 microcontroller** and transmitted via **XBee S2C Pro (Zigbee protocol)** to a central **ESP32 hub**, which controls irrigation based on sensor thresholds.

## Features
-✅ Real-time monitoring of soil parameters (temperature, moisture, NPK levels)
-✅ Wireless communication via **XBee S2C Pro (Zigbee protocol)**
-✅ **ATtiny85-based** low-power sensor node
-✅ Central **ESP32 hub** for data processing and decision-making
-✅ Automatic irrigation control based on soil conditions

## System Architecture
The system consists of multiple **sensor nodes** deployed in the field, each containing:
- **LM35DZ** – Soil temperature sensor
- **YL-69** – Soil moisture sensor
- **Soil NPK Sensor (RS485-JXBS-3001) with MAX485** – Measures nitrogen, phosphorus, and potassium levels
- **ATtiny85** – Microcontroller to read sensor data
- **XBee S2C Pro (Zigbee)** – Wireless communication module
- **Battery-powered operation** with **voltage regulation (AMS1117 3.3V)**

The **central hub** is an **ESP32** that receives data from multiple sensor nodes and **triggers irrigation** if a node falls below predefined soil moisture or nutrient thresholds.

## Hardware Components
| **Component**      | **Function** |
|--------------------|-------------|
| **LM35DZ**        | Soil temperature sensor |
| **YL-69**         | Soil moisture sensor |
| **Soil NPK Sensor (RS485-JXBS-3001)** | Measures soil nutrients (NPK) |
| **MAX485 Module** | Converts RS485 to UART for ATtiny85 |
| **ATtiny85**      | Reads sensor data and transmits via Zigbee |
| **XBee S2C Pro**  | Wireless Zigbee communication |
| **ESP32 (Central Hub)** | Receives data and controls irrigation |
| **AMS1117 3.3V**  | Voltage regulator for stable power |
| **Battery Module** | Power supply for sensor nodes |

## Circuit Diagram & PCB Design
The circuit and PCB were designed using **EasyEDA**.
📌 **Schematic & PCB Files:** [Link to EasyEDA project]

## Software & Communication
### 1️⃣ ATtiny85 Code (Sensor Node)
- Uses **SoftwareSerial** for communication with **MAX485 RS485 module**
- Reads data from **LM35DZ**, **YL-69**, and **Soil NPK sensor**
- Transmits sensor data via **XBee S2C Pro**

### 2️⃣ ESP32 Code (Central Hub)
- Receives data from multiple sensor nodes via **Zigbee**
- Compares sensor values with threshold values
- Controls irrigation system (valves, pumps) based on data

## Installation & Setup
### 1️⃣ Setting Up the Sensor Node
1. **Assemble the PCB** and connect all components as per the schematic.
2. **Flash the ATtiny85 code** using an **FTDI module**.
3. Power the system using a **3.7V Li-ion battery** with **AMS1117 voltage regulation**.

### 2️⃣ Setting Up the ESP32 Hub
1. Flash the **ESP32** with the central hub code.
2. Ensure the **XBee module is configured** to communicate with sensor nodes.
3. Deploy the hub in a central location for effective communication.

## Future Improvements
- 🔹 Integration with **LoRa for longer-range communication**
- 🔹 Cloud-based data storage & visualization
- 🔹 Solar-powered sensor nodes for sustainability

## Contributors
🚀 **[Your Name]** - Hardware design, PCB layout, and firmware development

## License
📜 MIT License - Feel free to use and modify this project.
