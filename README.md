# RESOURCE_MONITERING-AND-INTEGRATING_WITH_CLOUD
Resource monitoring using IoT (Internet of Things) and microcontrollers involves the deployment of sensor nodes equipped with various sensors to collect data on resources such as energy, water, air quality, temperature, humidity, and more enabling real-time data collection, analysis, and visualization..

# REQUIREMENTS 
 Hardware Modules:
* ESP32 Microcontroller: The ESP32 is a powerful microcontroller with built-in Wi-Fi and Bluetooth capabilities. It forms the core of the project, facilitating communication with sensors, connecting to Wi-Fi networks, and interfacing with the Blynk IoT platform.

* Ultrasonic Sensor (HC-SR04): This sensor measures distance by sending ultrasonic waves and calculating the time taken for the waves to bounce back. In this project, the HC-SR04 sensor is used to measure the water level in the tank.

* Temperature and Humidity Sensor (DHT11): The DHT11 sensor is a low-cost sensor capable of measuring temperature and humidity. It is used to monitor the temperature and humidity levels in the environment.

Software Modules (Libraries):
* Blynk Library for ESP32: This library enables the ESP32 microcontroller to communicate with the Blynk IoT platform. It provides functions to send and receive data from the Blynk server, allowing for remote monitoring and control of the device.

* DHT Sensor Library: The DHT sensor library provides functions to interface with DHT series sensors such as DHT11, DHT22, etc. It allows for reading temperature and humidity data from the DHT11 sensor.

* WiFi Library for ESP32: The WiFi library enables the ESP32 microcontroller to connect to Wi-Fi networks. It provides functions for configuring Wi-Fi settings, connecting to access points, and managing network connections.

* Blynk Timer Library: The Blynk timer library provides functions for scheduling tasks at regular intervals. It allows for executing specific functions periodically, such as reading sensor data and sending it to the Blynk server.

# Additional Resources:
Power Supply: The system requires a stable power supply to operate reliably. This could be provided through USB connections, battery packs, or external power sources depending on the application requirements.

Blynk IoT Platform Account: To use the Blynk IoT platform, users need to create an account on the Blynk website and obtain an authentication token, which is used to authenticate the device with the Blynk server.

# CODE EXPLANATION 
The code we've created helps monitor the water level in a tank and keeps track of temperature and humidity in a room. It uses an ESP32 microcontroller, which is like the brain of the system.

We have two types of sensors:

Ultrasonic Sensor: This sensor measures the distance from the top of the tank to the water level.
DHT11 Sensor: This sensor helps us know the temperature and humidity of the surrounding environment.
The code is written to connect our system to the internet using Wi-Fi. We've connected it to a platform called Blynk, which allows us to see the data from the sensors on our phones or computers from anywhere.

Here's what the code does step by step:

Initialization: It sets up the sensors and the Wi-Fi connection.
Sensor Readings: It reads the temperature and humidity from the DHT11 sensor and sends this information to the Blynk platform.
Water Level Measurement: It measures the distance from the top of the tank to the water level using the ultrasonic sensor and sends this data to the Blynk platform as well.
Loop: The code keeps doing these steps repeatedly, ensuring that we always have the latest information about the temperature, humidity, and water level.
This way, we can easily keep an eye on our water tank and the environment without having to check them physically. It's like having a smart assistant that tells us everything we need to know!
