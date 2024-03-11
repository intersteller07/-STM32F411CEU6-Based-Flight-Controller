STM32F411CEU6 Based Flight Controller
Welcome to the STM32F411CEU6 Drone build! 
I'm thrilled to present an open-source initiative aimed at unleashing the full potential of unmanned aerial vehicles (UAVs) using the STM32F411CEU6 microcontroller.

Before we start, I would like to thank INAV for providing the Flight configurator which made the more of an ease.

This is the unofficial target for INAV( Original source: https://github.com/iNavFlight/inav). Provides support for flight control boards that do not have official INAV support for the STM32F411CEU6 board. Whether or not to use this firmware is the user's responsibility and is free to do so. INAV developer link : https://github.com/iNavFlight/inav/tree/master/docs/development You can find all the details for firmware development here.



About INAV Flight Configurator:
iNav (inavflight) is an open-source firmware designed for the navigation and control of multirotors, fixed-wing aircraft, and other unmanned aerial vehicles (UAVs). It is based on the well-known Betaflight firmware but tailored for the unique requirements of GPS-assisted navigation and autonomous flight. Here's a brief overview of iNav Flight:

Features:
1. GPS Navigation:
iNav supports GPS modules to enable features such as Return-to-Home (RTH), waypoint navigation, and position hold.
2. Return-to-Home (RTH):
Automatic RTH capability allows the UAV to return to its takeoff location in case of signal loss or low battery.
3. Waypoint Navigation:
iNav enables the setting of waypoints for autonomous navigation, making it suitable for aerial surveying or exploration missions.
4. Altitude and Position Hold:
The firmware can maintain a specific altitude and position using the information from onboard sensors and GPS.
5. Barometer and Magnetometer Support:
iNav supports barometers and magnetometers for accurate altitude and heading information.
6. Fixed-Wing Support:
In addition to multirotors, iNav supports fixed-wing aircraft, providing a versatile solution for various aerial platforms.
7. On-Screen Display (OSD):
OSD integration allows real-time telemetry data to be displayed on the pilot's FPV goggles or monitor.
8. Mission Planning:
iNav is compatible with mission planning tools, allowing users to define complex flight plans before takeoff.
9. Telemetry and Blackbox Logging:
Telemetry support provides real-time information to the ground station, and Blackbox logging helps analyze and troubleshoot flight performance.
10. Configurability:
iNav offers a high level of configurability through its user-friendly interface, enabling users to tune parameters according to the specific requirements of their aircraft.


# STM32F411CEU6 INAV Firmware
STM32F411CEU6 Board Firmware
First, let's connect the board and the computer.
![image](https://user-images.githubusercontent.com/19993109/139479391-49dafee0-a7da-49ae-9196-10a578d4ac55.png)

# Download INAV Configurator
### As we are working on firmware 6.1, the configurator should be 6.1 or newer.
https://github.com/iNavFlight/inav-configurator/releases

# Windows
Download Configurator for Windows platform (win32 or win64 is present)
Extract ZIP archive
Run INAV Configurator app from unpacked folder
Configurator is not signed, so you have to allow Windows to run untrusted application.

# Install DFU Drivers (DFU mode)
## ImpulseRC Driver Fixer
https://impulserc.blob.core.windows.net/utilities/ImpulseRC_Driver_Fixer.exe
* Start ImpluseRC Driver Fixer
* Connect the FC USB to the PC While holding the boot button in. (DO NOT power on FC via external 5V or Vbat)
* The ImpulseRC Driver Fixer should then see and load the proper driver
* Start INAV configurator
* Connect the FC USB to the PC while holding the boot button in.
* INAV configurator should show it’s connected in DFU mode in the top right corner (DO NOT click the CONNECT button)
* Choose the latest hex file for your FC and then “Load Firmware local”. Once loaded, click “Flash Firmware”.

## For INAV 6.1 and newer versions New wire connection
### This firmware provides SOFTSERIAL support for Quadcopter and Plane. There is no extra servo support for Plane. Supports two extra servos for Quadcopter. The pin connections below are the same for both firmwares.

![Screenshot (8)](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/3973bad3-4eb7-4e81-a13e-29648c81f602)
![image](https://github.com/rizacelik/STM32F411CEU6_INAV_Firmware/assets/19993109/4eb16000-7abe-4209-af25-581cc869b4e0)

# Calibration of Accelerometer, Magnetometer and GPS

Firstly callibrate the Acclerometer and then the compass.
![Screenshot (9)](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/c0b666e1-f92a-4b55-bda9-e25869a2ed34)
![Screenshot (14)](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/73ecbde9-9270-4c44-afc2-5cc17c3b119e)

# setup of Ports
![Screenshot (12)](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/84e89add-532a-4fee-b8e9-c3c7e0d46347)

# Calibration for ESC

Instructions for setting throttle calibration for ESC high and low signal input:
1. Connect the ESC with the motor, connect the signal lead to the board according to the pin and motor port according to the diagram. You should do this for all of the motors you are going to use.
2. Open the INAV Configurator and connect to the flight control hub.
3. Adjust the gyroscope / accelerometer and magnometer calibration settings.
4. Turn on the remote control and enable the receiver protocol in the Receiver section. 
5. Go to the Output field and set the ESC output protocol according to you. We describe the setup for the STANDARD protocol.
6.To calibrate ESCs, make sure the propellers are off, flick on the “I understand” toggle, raise Master to full value, and plug in your battery.
7. The ESCs will go through their tones.
8. When the double beeping sound is heard (the highest point of the throttle is confirmed), move the throttle to the lowest point.
9. ESC calibration is considered done when three beeps mean OK.
10. Now unplug, plug in again, and raise Master very slowly until the motors are spinning comfortably.
![Screenshot (10)](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/a1a622bc-7170-4755-ac03-e041edc26949)
![Screenshot (11)](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/2ccc622f-8d67-44a6-bc8b-0aa47e460219)
This video will guide you https://www.youtube.com/watch?v=1IrgbY0YhqM

# GY-87 10DOF Module MPU6050 HMC5883L BMP180
![image](https://user-images.githubusercontent.com/19993109/139479938-a1166d41-17c8-41a2-8903-195406ecd020.png)

# Support Receiver Types
![image](https://user-images.githubusercontent.com/19993109/202130179-ef0616bc-785d-4cfc-98a4-097b3db7d4aa.png)

# SBUS Signal Inverter
The inverter is easy to make, only requires 2 resistors (10K ohm and 4.7K ohm), 1 transistor (BC547b), and one servo cable. These are all very cheap and easy to find.

![image](https://github.com/rizacelik/STM32F411CEU6_INAV_Firmware/assets/19993109/ab6d0c71-d6ce-4dff-9e2d-8936900b9bbe)

# WS2811 5 Volt Led Strip
There must be a 5V external voltage source. Don't buy from board source, you will burn the microcontroller.
![image](https://github.com/rizacelik/STM32F411CEU6_INAV_Firmware/assets/19993109/7cbca6a2-a52e-4717-baac-76d49ab18dff)
![image](https://github.com/rizacelik/STM32F411CEU6_INAV_Firmware/assets/19993109/01d31dc0-9265-437c-8cec-c1dc0161a9a5)

# My Build
![WhatsApp Image 2024-03-12 at 03 05 01_5064bebf](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/5a7da183-2c2b-4e78-a5a5-e86f88732792)
![WhatsApp Image 2024-03-12 at 03 05 00_37f0d6ef](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/e70871b4-0bb8-4622-ab48-3a74bd903b4d)
![WhatsApp Image 2024-03-12 at 03 05 00_51d5ef29](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/1b0b717e-5fda-4690-87a3-32a3be922d58)
![WhatsApp Image 2024-03-12 at 03 05 01_5064bebf](https://github.com/intersteller07/-STM32F411CEU6-Based-Flight-Controller/assets/114882504/3c1f8b9f-ec1f-485b-bd77-5962ab3035b3)


