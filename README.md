# Astro Pi
Project for IoT lessons at AGH UST.

We've been given a Raspberry Pi with Sense Hat detectors used for Astro Pi projects.
Project assumes setting our Pi as a LWM2M server and exposing some made-up astro object.

There has been defined and exposed one LWM2M object (3300, Generic Sensor) with three instances representing following resources:
- (0) Level of charging power (Astro-ship batteries are charged using solar panels and we're exposing how much does the ship is faced towards the sun)
- (1) Planet we are currently at (using atmospheric data collected by sensors)
- (2) Number of astronauts on the ship (uses camera to take a picture and OpenCV to detect people at it)

# Implementation
Implementation of these resources takes place in python files called ResourceHandlers.
- SensorValue (ResourceHandler 5700) is responsible for computing actual values. It contains business logic and computes it depending on instance_id passed as an argument to the read() function
- Application_Type (ResourceHandler 5750) represents an application type and contains description of every instance
- Sensor_Unit (ResourceHandler 5701) represents the sensor units, so it defines the meaning of values returned by sensor value ResourceHandler

# Project in action
The svetovid service has to be enabled at the Raspberry Pi. (https://github.com/AVSystem/Svetovid-raspberry-client)
Then a web browser LWM2M client Coyote can connect to this device and read values from our generic and other basic sensors.


# Authors
- Krzystof Siekierzyński (https://github.com/ksiek127)
- Tomasz Koszarek (https://github.com/koszar91)
- Szymon Rynkownski (https://github.com/rynkow)
- Jakub Koźlak (https://github.com/kkoz3434)
- Kamil Pluciński (https://github.com/K4m1lP)
- Paweł Holowicki (https://github.com/Gajkes)
