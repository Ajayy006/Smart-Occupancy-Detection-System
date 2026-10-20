# Smart Occupancy Detection System Using MSP430 and ESP32

An embedded systems and Internet of Things (IoT) project designed to detect human presence and monitor room occupancy using an MSP430 microcontroller, a PIR motion sensor, and an ESP32 Wi-Fi module.

## 📌 Project Overview

The Smart Occupancy Detection System automatically identifies whether a room or monitored area is occupied or vacant. The PIR sensor detects human movement, and the MSP430 processes the sensor signal to determine the occupancy status. The ESP32 provides wireless connectivity to transmit occupancy information to an IoT monitoring platform.

This project demonstrates the integration of embedded systems, sensor interfacing, UART communication, and Wi-Fi-based monitoring for smart building applications.

## 🎯 Objectives

- Detect human movement using a PIR motion sensor.
- Process sensor data using the MSP430 microcontroller.
- Indicate occupancy status through an LED.
- Transfer occupancy information from the MSP430 to the ESP32 using UART communication.
- Enable remote occupancy monitoring through Wi-Fi and an IoT platform.
- Demonstrate the potential of occupancy monitoring for energy-efficient buildings.

## ⚙️ Hardware Components

| Component | Purpose |
|---|---|
| MSP430 LaunchPad | Processes sensor input and determines occupancy status |
| ESP32 Wi-Fi module | Provides wireless communication |
| HC-SR501 PIR motion sensor | Detects human movement |
| LED | Provides visual occupancy indication |
| 220 Ω resistor | Limits LED current |
| Buzzer | Optional audible indication |
| Breadboard | Supports circuit assembly |
| Jumper wires | Establish electrical connections |
| USB cable | Programming and power supply |
| Suitable 3.3 V supply | Powers the ESP32 module as required |

## 💻 Software and Technologies

- Embedded C/C++
- Arduino IDE with the appropriate ESP32 board support, if used
- MSP430 development environment compatible with the selected microcontroller
- UART serial communication
- Wi-Fi connectivity
- ThingSpeak IoT platform, if configured

## 🧩 System Architecture

The system follows this sequence:

1. **Sensing:** The PIR sensor detects human movement in the monitored area.
2. **Processing:** The MSP430 reads the sensor output and determines the occupancy condition.
3. **Indication:** The LED provides a visual indication of the detected condition.
4. **Communication:** The MSP430 transmits occupancy status to the ESP32 through UART.
5. **Wireless monitoring:** The ESP32 connects to Wi-Fi and sends occupancy data to the configured IoT platform.
6. **Monitoring:** The user can view the occupancy information remotely.

## 🔄 Communication Between Controllers

The ESP32 firmware is designed to receive the following text messages from the MSP430:

- `OCCUPIED` — occupancy detected.
- `VACANT` — no occupancy detected.

The ESP32 uses UART2 with a configured baud rate of 9600 and receives data through GPIO 16 in the example firmware.

For ThingSpeak monitoring, the ESP32 converts the occupancy status into a numerical value:

| Occupancy status | Field 1 value |
|---|---:|
| OCCUPIED | 1 |
| VACANT | 0 |

The ESP32 then sends the value to the ThingSpeak channel using its configured write API key.


## 🛠️ Setup and Implementation

1. Assemble the circuit according to the verified hardware connections.
2. Connect the PIR sensor to the configured MSP430 input.
3. Program the MSP430 using the appropriate development environment.
4. Configure the ESP32 board in the Arduino IDE or the environment used for your implementation.
5. Set up the UART connection between the two controllers.
6. Configure Wi-Fi credentials locally and configure ThingSpeak credentials if cloud monitoring is enabled.
7. Upload the firmware to the corresponding boards.
8. Open the Serial Monitor and verify that the occupancy messages are received.
9. If ThingSpeak is configured, verify that the occupancy values appear in the correct channel field.

**Note:** Pin assignments and board configuration must match the actual hardware. Verify the connection details before reproducing the project.

## 📊 Results and Testing

The project is designed to identify occupancy conditions using a PIR sensor and communicate the resulting status through the MSP430 and ESP32.

Add the following implementation evidence to the `Results/` folder as available:

- Occupancy detection output
- Vacant-room output
- Serial communication output
- IoT dashboard screenshots, if implemented
- Hardware implementation photographs

## 🌐 Applications

- Smart classrooms and educational institutions
- Office and meeting-room occupancy monitoring
- Laboratories and workspaces
- Smart home systems
- Smart building monitoring
- Occupancy-based energy management

## 🚀 Future Enhancements

- Automatic lighting and fan control
- Occupancy history and cloud-based data logging
- Real-time notifications
- Integration of multiple sensors
- Improved detection and energy-saving strategies
- A dedicated dashboard for occupancy visualization

## 🎥 Project Demonstration

[Watch the project demonstration on YouTube](https://youtu.be/p-WfVClxeYo)


Department of Electronics and Communication Engineering

## 📚 References

Refer to the project report for the bibliography, including related work on IoT-based smart rooms, occupancy monitoring, energy management, and the MSP430 microcontroller family.

## 🔐 Security Notice

Never commit Wi-Fi passwords, API keys, or other private credentials to a public repository. Use placeholders in example code and keep real credentials in a local configuration file excluded from version control.

