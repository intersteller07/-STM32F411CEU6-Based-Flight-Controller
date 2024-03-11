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
Configurator is not signed, so you have to allow Windows to run untrusted application. There might be a monit for it during first run

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


