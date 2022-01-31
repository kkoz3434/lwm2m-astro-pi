# Astro Pi
Project for IoT lessons at AGH UST.

We've been given a Raspberry Pi with Sense Hat detectors used for Astro Pi projects.
Project assumes setting our Pi as a LWM2M server and exposing some made-up astro resources.
There has been defined and exposed one LWM2M object with three instances corresponding to following resources:
- Number of astronauts on the ship (uses camera to take a picture and OpenCV to detect people at it)
- Level of charging power (Astr-ship batterias are charged using solar panels and we're extending how much does the ship is faced towards the sun)
- Planet we are currently at (using atmospheric data collected by sensors)

# Implementation
Business logic we implemented is mainly in 5670 Resource Handler.
It computes a LWM2M response to the client's request.
5671 and 3456 Resource Handlers are implemented as well, they return a response of name and unit of our resources.

# Authors
@koszar91, ...

