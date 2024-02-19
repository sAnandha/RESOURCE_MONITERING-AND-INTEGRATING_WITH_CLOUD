# RESOURCE_MONITERING-AND-INTEGRATING_WITH_CLOUD
Resource monitoring using IoT (Internet of Things) and microcontrollers involves the deployment of sensor nodes equipped with various sensors to collect data on resources such as energy, water, air quality, temperature, humidity, and more enabling real-time data collection, analysis, and visualization..

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
