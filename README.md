# Water-Level-Indicator

Water Level Indicator using Ultra-Sonic Sensor on Raspberry pi 3

The ultrasonic sensor I picked is the HC-SR04, which has four associations that are wired to the GPIO pins of the Raspberry Pi. With the assistance of a Python content, the sensor, which is mounted inside the sump pit confronting the water, sends a sound heartbeat that reflects off the water and back to the sensor. The content screens the measure of time it takes for the sound heartbeat to skip back to the sensor. It ascertains the separation by estimating the time required for the beat to return at the speed of sound. This gives you a perusing of the separation between the sensor and the water. The separation is utilized to figure the water profundity and log a period

In this project I chose GPIO 4 you can use any other pin.
Pin 1 provides 5V of power to the HC-SR04 sensor. A command is initiated on GPIO17 (Trig) that sets the value of the pin to True for 10 micro seconds. This causes the sensor to initiate a series of sound pulses toward the water for that short amount of time. The Echo pin connected to GPIO27 listens for a return pulse. The difference between the send and the return of the pulse gives a time measurement. The measurement is used to calculate the distance of the water.
This causes a small problem as Raspberry Pi GPIO pins are rated only for 3.3V. The sensor sends a 5V current back toward GPIO27. A way is needed to throttle the current to 3.3V, which won't damage the Pi. To protect the Pi from damage, simply insert a voltage divider on the Echo line between the sensor and the Pi.
