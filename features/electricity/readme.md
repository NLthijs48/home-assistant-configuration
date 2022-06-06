# Electricity

Monitoring the power usage of our DSMR 5.0 electricity meter using a small module from zuidwijk.com (the ethernet version 3.2).
It connects to the P1 port of the meter, needs power input, and connects to ethernet.
The DSMR module in Home Assistant can connect to this device and gets readings from it.

Since my Raspberry Pi that runs Home Assistant is located at my home cinema setup I cannot connect it directly using a P1 -> USB cable.
I want to keep the Raspberry Pi connected to my TV+receiver using HDMI for CEC control (the api/integration of my Philips TV is bad, but HDMI-CEC works like a charm).

# Hardware
- [P1 reader ethernet v3.2](https://www.zuidwijk.com/product/p1-reader-ethernet/)
  - Reads electricity usage from the smart meter in my house (The Netherlands) using DSMR 5.0 
  - Note that a [new version](https://www.zuidwijk.com/product/slimmelezer-plus/) is available that is even nicer 
- A lot of [Shelly Plug S](https://shelly.cloud/products/shelly-plug-s-smart-home-automation-device/)
  - Measure power usage of a bunch of devices
  - Some of them used to create a state machine of devices (see washing_machine feature package)

# Software
- [DSMR Slimme Meter](https://www.home-assistant.io/integrations/dsmr)
  - Works easily with the P1 reader hardware
- [Shelly integration](https://www.home-assistant.io/integrations/shelly/)