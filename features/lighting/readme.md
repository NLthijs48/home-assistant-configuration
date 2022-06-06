# Lighting

Everything to automate lighting as much as possible

### Hardware
- [Conbee II](https://www.phoscon.de/en/conbee2) Xigbee stick
  - Using a 3m USB cable extension, less interference
- Ikea FLOALT panel WS 30x30
- Ikea FLOALT panel WS 90x30
- Ikea TRADFRI bulb E27 CWS opal 600lm
  - Color version
- Ikea TRADFRI bulb E27 W opal 1000lm
  - Used in hallways/closets
- Ikea TRADFRI bulb GU10 W 400lm
  - Spots used in the living room and a bedroom
- Ikea TRADFRI remotes
- [Ikea TRADFRI Smart outlet](https://www.ikea.com/nl/en/p/tradfri-wireless-control-outlet-smart-90356166/)
  - Simple but bulky outlets
  - Support a full 16A @ 230V
- [Hue motion sensor](https://www.philips-hue.com/nl-be/p/hue-bewegingssensor/8719514342125)
  - Have a short reset time of ~5 seconds before they can sense motion again
  - Detection is quicker than the Ikea ones
  - Have a light sensor
  - Have a temperature sensor
- [Hue outdoor motion sensor](https://www.philips-hue.com/en-us/p/hue-outdoor-sensor/046677541736)
- [Hue indoor ledstrip](https://zigbee.blakadder.com/Philips_LST002.html)
- [Gledopto GL-C-008](https://www.gledopto.com/h-col-324.html), bought [here](https://www.ledstripkoning.nl/speciale-leds/zigbee-philips-hue-controller/losse-zigbee-controllers/losse-zigbee-controller-voor-rgbww-led-strips-te-bedienen-met-philips-hue/)
  - Controls a LED strip along a bed
  - Has issues with brightness below ~20%, will just turn off


### Software
- [ZHA integration](https://www.home-assistant.io/integrations/zha)
  - Runs the whole Zigbee network

### Features
- Light groups for lights that are in the same armature
- Light groups for lights in the same area or room
- Automatic living room lights based on presence
- Smart turn-on brightness based on the time of the day
- Summary UI for on the home screen
- Detailed UI for all lights
