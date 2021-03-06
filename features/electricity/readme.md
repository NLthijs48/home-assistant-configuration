# Electricity

Monitoring the power usage of our DSMR 5.0 electricity meter using a small module from zuidwijk.com (the ethernet version 3.2).
It connects to the P1 port of the meter, needs power input, and connects to ethernet.
The DSMR module in Home Assistant can connect to this device and gets readings from it.

Since my Raspberry Pi that runs Home Assistant is located at my home cinema setup I cannot connect it directly using a P1 -> USB cable.
I want to keep the Raspberry Pi connected to my TV+receiver using HDMI for CEC control (the api/integration of my Philips TV is bad, but HDMI-CEC works like a charm).
